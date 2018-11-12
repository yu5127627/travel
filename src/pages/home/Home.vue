<template>
    <div>
        <home-header></home-header>
        <home-swiper :list="swiperList"></home-swiper>
        <home-icons :list="iconsList"></home-icons>
        <home-recommend :list="recommendList"></home-recommend>
        <home-weekend :list="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader: HomeHeader,
    HomeSwiper: HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      swiperList: [],
      iconsList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.swiperList = res.data.swiperList
        this.iconsList = res.data.iconsList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
