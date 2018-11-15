<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <div class="city-main">
            <city-item
                    :hotCity="hotCity"
                    :cityAll="cityAll"
                    :letter="letter"
            >
            </city-item>
        </div>
    </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityItem from './components/CityItem'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityItem
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
      axios.get('./static/mock/city.json')
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
    // 初始化页面后调用
    this.getCityList()
  }
}
</script>

<style lang="stylus" scoped>
    .city-main {
        position: relative;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
    }
</style>
