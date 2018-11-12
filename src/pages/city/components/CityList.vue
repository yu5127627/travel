<template>
    <div ref="web">
        <div class="city-list">
            <div class="list-city" v-for="(city,key) of cityAll" :key="key" :ref="key">
                <div v-text="key"></div>
                <ul class="list-city-ul">
                    <li v-for="list of city"
                        class="list-city-li"
                        v-text="list.name"
                        :key="list.id">
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cityAll: Object,
    letter: String
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        console.log(element)
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.web)
  }
}
</script>

<style lang="stylus" scoped>
    .city-list{
        position: absolute;
        top: 8rem;
        left: 0;
        right: 0;
        background-color: #fff;
    }
    .list-city>div{
        height: .7rem;
        background-color: rgb(245,245,245);
        font-size: .244rem;
        font-weight: 400;
        line-height: .7rem;
        text-indent: .2rem;
    }
    .list-city-ul{
        overflow: hidden;
    }
    .list-city-li{
        width: 24.72%;
        height: .9rem;
        line-height: .9rem;
        font-size: .3rem;
        font-weight: 300;
        float: left;
        display: inline-block;
        text-align: center;
        background-color: rgba(0,188,212,.4);
        border-bottom: .02rem solid #fff;
        border-right: .02rem solid #fff;
        overflow: hidden;
    }
    .list-city-li:nth-child(4n){
        border-right: none;
    }
</style>
