<template>
    <div>
      <home-header ></home-header>
      <home-swiper :swiperList="swiperList"></home-swiper>
      <home-icons :iconList="iconList"></home-icons>
      <home-recommend :recommendList="recommendList"></home-recommend>
      <home-weekend :weekendList="weekendList"></home-weekend>
    </div>
</template>

<script>
  import {mapState} from 'vuex'
  import HomeHeader from './components/Header'
  import HomeSwiper from './components/Swiper'
  import HomeIcons from './components/Icons'
  import HomeRecommend from './components/Recommend'
  import HomeWeekend from './components/Weekend'
  import axios from 'axios'
    export default {
        name: "home",
        data () {
          return {
            lastCity: '',
            swiperList: [],
            iconList: [],
            recommendList: [],
            weekendList: []
          }
        },
        components : {
          HomeHeader,
          HomeSwiper,
          HomeIcons,
          HomeRecommend,
          HomeWeekend
      },
      mounted() {
          this.lastCity = this.city;
          this.getHomeInfo()
      },
      activated() {
          if (this.lastCity !== this.city) {
            this.lastCity = this.city;
            this.getHomeInfo();
          }
      },
      computed : {
          ...mapState(['city'])
      },
      methods : {
          getHomeInfo : function () {
            axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc)
          },
          getHomeInfoSucc : function (res) {
            res = res.data;
            if (res.ret && res.data)
            {
              const data = res.data;
              this.swiperList = data.swiperList;
              this.iconList = data.iconList;
              this.recommendList = data.recommendList;
              this.weekendList = data.weekendList;
            }
          }
      }
    }
</script>

<style scoped>

</style>
