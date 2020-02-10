<template>
  <div class="recommend">
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li
        class="border-bottom"
        v-for="item of recommendList"
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
    data () {
      return {
        recommendList : [
          {
            id : '0001',
            imgUrl : 'https://imgs.qunarzz.com/sight/source/1505/86/57819390ea997c.jpg_r_640x214_00888590.jpg',
            title : '澳门水舞间演出'
            ,desc : '澳门水舞间演出，浪漫的主题演出'
          }, {
            id : '0002',
            imgUrl : 'https://imgs.qunarzz.com/sight/source/1505/86/57819390ea997c.jpg_r_640x214_00888590.jpg',
            title : '澳门水舞间演出'
            ,desc : '澳门水舞间演出，浪漫的主题演出'
          }, {
            id : '0003',
            imgUrl : 'https://imgs.qunarzz.com/sight/source/1505/86/57819390ea997c.jpg_r_640x214_00888590.jpg',
            title : '澳门水舞间演出'
            ,desc : '澳门水舞间演出，浪漫的主题演出'
          }, {
            id : '0004',
            imgUrl : 'https://imgs.qunarzz.com/sight/source/1505/86/57819390ea997c.jpg_r_640x214_00888590.jpg',
            title : '澳门水舞间演出'
            ,desc : '澳门水舞间演出，浪漫的主题演出'
          },
        ]
      }
    }
  }
</script>

<style scoped lang="stylus">
  @import "~styles/mixins.styl"
  .recommend-title
    margin-top: .2rem
    line-height: .8rem
    text-indent: .2rem
    background-color: #eee;
  .item-img-wrapper
    overflow: hidden;
    height:0
    padding-bottom: 33.9%
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
