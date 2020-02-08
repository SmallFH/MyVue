<template>
  <div class="wiper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
    export default {
        name: "HomeSwiper",
        data () {
          return {
            swiperOption : {
              pagination : '.swiper-pagination',
              loop: true
            },
            swiperList : [
              {
                id : '0001',
                imgUrl : '//imgs.qunarzz.com/vc/6d/9f/35/b8ad5468f73fd60ec0ced086f6.jpg_92.jpg'
              },{
                id : '0002',
                imgUrl : '//imgs.qunarzz.com/vc/ad/7c/fe/037d1a400372ff57b0030d1d1c.jpg_92.jpg'
              }
              ]
          }
      }
    }
</script>

<style scoped lang="stylus">
  .wiper >>> .swiper-pagination-bullet-active
    background-color: #fff;
  .wiper
    width:100%
    height:0
    overflow: hidden
    padding-bottom : 31.25%
    background-color: #eee;
    .swiper-img
     width : 100%
</style>
