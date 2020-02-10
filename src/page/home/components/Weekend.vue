<template>
  <div class="recommend">
    <div class="recommend-title">周末去哪儿</div>
    <ul v-if="showWeekendList">
      <li
        class="border-bottom"
        v-for="item of weekendList"
        :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imgUrl" class="item-img">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "HomeWeekend",
    props: {
      weekendList : Array
    },
    computed : {
      showWeekendList : function () {
        return this.weekendList.length;
      }
    }
  }
</script>

<style scoped lang="stylus">
  @import "~styles/mixins.styl"
  .recommend-title
    margin-top: .1rem
    line-height: .8rem
    text-indent: .2rem
    background-color: #eee;
  .item-img-wrapper
    overflow: hidden;
    height:0
    padding-bottom: 37.09%
    .item-img
      width: 100%
  .item-info
    padding:.1rem
    .item-title
      line-height: .54rem
      font-size : .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      color: #ccc
      ellipsis()

</style>
