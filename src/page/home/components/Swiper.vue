<template>
  <div class="wiper">
    <swiper :options="swiperOption" v-if="showSwiper">
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
        props : {
          swiperList : Array
        },
        computed : {
          showSwiper: function () {
            return this.swiperList.length
          }
        },
        data () {
          return {
            swiperOption : {
              pagination : '.swiper-pagination',
              loop: true
            },
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
