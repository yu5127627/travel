<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :hotCity="hotCity"
                   :citySort="citySort"
                   :cityAs="cityAs"
                   :cityBs="cityBs"
                   :cityCs="cityCs"
                   :cityDs="cityDs"
                   :cityEs="cityEs"
                   :cityFs="cityFs"
                   :cityGs="cityGs"
                   :cityHs="cityHs"
                   :cityJs="cityJs"
                   :cityKs="cityKs"
                   :cityLs="cityLs"
                   :cityMs="cityMs"
                   :cityNs="cityNs"
                   :cityPs="cityPs"
                   :cityQs="cityQs"
                   :cityRs="cityRs"
                   :citySs="citySs"
                   :cityTs="cityTs"
                   :cityUs="cityUs"
                   :cityVs="cityVs"
                   :cityWs="cityWs"
                   :cityXs="cityXs"
                   :cityYs="cityYs"
                   :cityZs="cityZs"
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
      citySort: [],
      cityAs: [],
      cityBs: [],
      cityDs: [],
      cityEs: [],
      cityFs: [],
      cityGs: [],
      cityHs: [],
      cityJs: [],
      cityKs: [],
      cityLs: [],
      cityMs: [],
      cityNs: [],
      cityPs: [],
      cityQs: [],
      cityRs: [],
      citySs: [],
      cityTs: [],
      cityUs: [],
      cityVs: [],
      cityWs: [],
      cityXs: [],
      cityYs: [],
      cityZs: []
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
        this.citySort = res.data.citySort
        this.cityAs = res.data.cities.A
        this.cityBs = res.data.cities.B
        this.cityCs = res.data.cities.C
        this.cityDs = res.data.cities.D
        this.cityEs = res.data.cities.E
        this.cityFs = res.data.cities.F
        this.cityGs = res.data.cities.G
        this.cityHs = res.data.cities.H
        this.cityJs = res.data.cities.J
        this.cityKs = res.data.cities.K
        this.cityLs = res.data.cities.L
        this.cityMs = res.data.cities.M
        this.cityNs = res.data.cities.N
        this.cityOs = res.data.cities.O
        this.cityPs = res.data.cities.P
        this.cityQs = res.data.cities.Q
        this.cityRs = res.data.cities.R
        this.citySs = res.data.cities.S
        this.cityTs = res.data.cities.T
        this.cityUs = res.data.cities.U
        this.cityVs = res.data.cities.V
        this.cityWs = res.data.cities.W
        this.cityXs = res.data.cities.X
        this.cityYs = res.data.cities.Y
        this.cityZs = res.data.cities.Z
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
