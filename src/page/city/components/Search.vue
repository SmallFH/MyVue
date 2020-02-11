<template>
  <div>
      <div class="search">
        <input v-model="keyword" type="text" placeholder="输入城市名/拼音" class="search-input">
      </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有匹配的城市</li>
      </ul>
    </div>
  </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
        name: "CitySearch",
        data () {
            return {
              keyword : '',
              list : [],
              timer : null
            }
        },
        mounted () {
          this.scroll = new Bscroll(this.$refs.search)
        },
        props : {
          cities : Object
        },
        watch : {
            keyword () {
              if (this.timer) {
                clearTimeout(this.timer)
              }
              if (!this.keyword) {
                this.list = [];
                return;
              }
              this.timer = setTimeout(() => {
                const result = [];
                for (let i in this.cities) {
                  this.cities[i].forEach( (value) => {
                    if (
                      value.spell.indexOf(this.keyword) > -1 ||
                      value.name.indexOf(this.keyword) >-1 ) {
                      result.push(value);
                    }
                  })
                }
                this.list =result;
              }, 100)
            }
        },
        computed : {
          hasNoData () {
            return !this.list.length
          }
        }
    }
</script>

<style scoped lang="stylus">
  @import "~styles/variables.styl"
  .search
    height: .72rem
    padding: .1rem
    background-color: $bgColor
    .search-input
      box-sizing : border-box
      width: 100%
      height: .62rem
      line-height: .62rem
      text-align : center
      padding: 0 .1rem
      color: #666
      border-radius : .06rem
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.68rem
    left:0
    right:0
    bottom:0
    background-color: #eee;
    .search-item
      line-height: .62rem
      padding-left : .2rem
      background-color: #fff;
      color: #666


</style>
