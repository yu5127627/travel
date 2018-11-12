<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <div class="city-list" ref="wrapper">
            <div class="wrapper">
                <city-hot :hotCity="hotCity"></city-hot>
                <city-list :cityAll="cityAll"></city-list>
            </div>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityHot from './components/cityHot'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityHot
  },
  data () {
    return {
      hotCity: [],
      cityAll: {}
    }
  },
  methods: {
    getCityList () {
      axios.get('/api/city.json')
        .then(this.getCityListSucc)
    },
    getCityListSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.hotCity = res.data.hotCities
        this.cityAll = res.data.cities
      }
    }
  },
  mounted () {
    // vue 完全加载完毕才会执行的钩子函数
    this.scroll = new BScroll(this.$refs.wrapper)
    // 初始化页面后调用
    this.getCityList()
  }
}
</script>

<style lang="stylus" scoped>
    .wrapper{
        position: absolute;
        top: 1.48rem;
        left: 0;
        right: 0;
        z-index: -1;
    }
</style>
