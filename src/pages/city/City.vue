<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :hotCity="hotCity"
                   :cityAll="cityAll"
        ></city-list>
    </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList
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
    // 初始化页面后调用
    this.getCityList()
  }
}
</script>

<style lang="stylus" scoped>

</style>
