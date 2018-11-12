<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <div ref="wrapper">
            <div class="wrapper">
                <city-hot :hotCity="hotCity"></city-hot>
                <city-sort :cityAll="cityAll" @change="handleLetterChange"></city-sort>
                <city-list :cityAll="cityAll" :letter="letter"></city-list>
            </div>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityHot from './components/CityHot'
import CitySort from './components/Citysort'
import CityList from './components/CityList'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityHot,
    CitySort,
    CityList
  },
  data () {
    return {
      hotCity: [],
      cityAll: {},
      letter: ''
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
    },
    handleLetterChange (letter) {
      this.letter = letter
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
