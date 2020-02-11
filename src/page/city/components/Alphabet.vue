<template>
  <ul class="list">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @click="getClickLetter"
      @touchstart="handTouchStart"
      @touchmove="handTouchMove"
      @touchend="handTouchEnd"
    >{{item}} </li>
  </ul>
</template>

<script>
    export default {
        name: "CityAlphabet",
        props : {
          cities : Object
        },
        computed : {
          letters () {
            const letters = [];
            for (let i in this.cities) {
              letters.push(i)
            }
            return letters;
          }
        },
        data () {
          return {
            touchStatus : false,
            startY : 0,
            timer : null
          }
        },
        updated () {
          this.startY = this.$refs['A'][0].offsetTop;
        },
        methods : {
          getClickLetter (e) {
            this.$emit('clickLetter', e.target.innerText);
          },
          handTouchStart () {
            this.touchStatus = true
          },
          handTouchMove (e) {
            if (this.touchStatus) {
              if (this.timer) {
                clearTimeout(this.timer)
              }
              this.timer = setTimeout( () => {
                const touchY = e.touches[0].clientY - 79;
                const index = Math.floor((touchY - this.startY) / 20);
                if (index >= 0 && index <= this.letters.length) {
                  this.$emit('clickLetter', this.letters[index])
                }
              }, 16)
            }
          },
          handTouchEnd () {
            this.touchStatus = false
          }
        }
    }
</script>

<style scoped lang="stylus">
  @import "~styles/variables.styl"
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.68rem
    right: 0
    bottom: 0
    width: .4rem
    .item
      text-align center
      line-height .4rem
      color: $bgColor


</style>
