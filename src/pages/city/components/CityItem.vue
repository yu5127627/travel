<template>
    <div ref="web"  class="city-item">
        <div>
            <!-- 热门城市 -->
            <div class="city-hot">
                <div class="hot-city">热门城市</div>
                <ul class="hot-city-ul">
                    <li class="hot-city-li"
                        v-for="item of hotCity"
                        v-text="item.name"
                        :key="item.id"
                        @click="handleValue(item.name)"
                    ></li>
                </ul>
            </div>
            <!-- 城市字母排序 -->
            <div class="city-sort">
                <div class="sort-city">字母排序</div>
                <ul class="sort-city-ul">
                    <li class="sort-city-li"
                        v-for="(sort,key) of cityAll"
                        :key="key"
                        :ref="key"
                        @click="handleClick"
                    >
                        {{ key }}
                    </li>
                </ul>
            </div>
            <!-- 所有城市 -->
            <div class="city-list">
                <div class="list-city"
                     v-for="(city,key) of cityAll"
                     :key="key"
                     :ref="key"
                >
                    <div v-text="key"></div>
                    <ul class="list-city-ul">
                        <li v-for="list of city"
                            class="list-city-li"
                            v-text="list.name"
                            :key="list.id"
                            @click="handleValue(list.name)"
                        >
                        </li>
                    </ul>
                </div>
            </div>
            <!-- 返回顶部 -->
        </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityItem',
  props: {
    hotCity: Array,
    cityAll: Object
  },
  data () {
    return {
      letter: ''
    }
  },
  methods: {
    handleValue (val) {
      this.$store.dispatch('changeCity', val)
      this.$router.push('/')
    },
    handleClick (e) {
      this.letter = e.target.innerText
    }
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][1]
        console.log(element)
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.web, {click: true})
  }
}
</script>

<style lang="stylus" scoped>
    .city-item{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: -1;
    }
    /* 热门城市 */
    .hot-city,.sort-city,.list-city>div{
        height: .7rem;
        background-color: rgb(245,245,245);
        font-size: .244rem;
        font-weight: 400;
        line-height: .7rem;
        text-indent: .2rem;
    }
    .hot-city-ul,.sort-city-ul,.list-city-ul{
        overflow: hidden;
    }
    .hot-city-li,.sort-city-li,.list-city-li{
        height: .9rem;
        line-height: .9rem;
        font-size: .3rem;
        font-weight: 300;
        float: left;
        text-align: center;
        background-color: rgba(0,188,212,.4);
        border-bottom: .02rem solid #fff;
        border-right: .02rem solid #fff;
    }
    .hot-city-li {
        width: 33.1%;
    }
    .hot-city-li:nth-child(3n){
        border-right: none;
    }
    /* 城市字母排序 */
    .sort-city-li{
        width: 19.73%;
    }
    .sort-city-li:nth-child(5n){
        border-right: none;
    }
    /* 所有城市 */
    .list-city-li{
        width: 24.72%;
    }
    .list-city-li:nth-child(4n){
        border-right: none;
    }
</style>
