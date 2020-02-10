<template>
    <div class="recommend">
      <div class="recommend-title">热销推荐</div>
      <ul>
        <li
          class="item border-bottom"
          v-for="item of recommendList"
          :key="item.id">
          <img :src="item.imgUrl" class="item-img">
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-btn">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
    export default {
        name: "HomeRecommend",
        data () {
          return {
            recommendList : [
              {
                id : '0001',
                imgUrl : 'https://imgs.qunarzz.com/sight/p0/1801/5d/5d24bb249f8ca889a3.water.jpg_200x200_77551cb9.jpg',
                title : '澳门水舞间演出'
                ,desc : '澳门水舞间演出，浪漫的主题演出'
              }, {
                id : '0002',
                imgUrl : 'https://imgs.qunarzz.com/sight/p0/1801/5d/5d24bb249f8ca889a3.water.jpg_200x200_77551cb9.jpg',
                title : '澳门水舞间演出'
                ,desc : '澳门水舞间演出，浪漫的主题演出'
              }, {
                id : '0003',
                imgUrl : 'https://imgs.qunarzz.com/sight/p0/1801/5d/5d24bb249f8ca889a3.water.jpg_200x200_77551cb9.jpg',
                title : '澳门水舞间演出'
                ,desc : '澳门水舞间演出，浪漫的主题演出'
              }, {
                id : '0004',
                imgUrl : 'https://imgs.qunarzz.com/sight/p0/1801/5d/5d24bb249f8ca889a3.water.jpg_200x200_77551cb9.jpg',
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
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 2rem
      height: 2rem
      padding: .1rem
    .item-info
      flex:1
      padding:.1rem
      min-width:0
      .item-title
        line-height: .54rem
        font-size : .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-btn
        line-height: .44rem
        margin-top: .16rem
        background-color: #ff9300;
        padding: 0 .1rem
        border-radius: .06rem
        color: #fff
</style>
