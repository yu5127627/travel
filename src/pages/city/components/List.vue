<template>
    <div>
        <div class="sort-city">字母排序</div>
        <ul class="sort-city-ul">
            <li class="sort-city-li"
                v-for="(sort,key) of cityAll"
                :key="key"
                :ref="key"
                @click="handClick"
            >
                {{ key }}
            </li>
        </ul>
        <div v-for="(city,key) of cityAll" :key="key">
            <div class="a-city" v-text="key"></div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="item of city"
                    v-text="item.name"
                    :key="item.id"
                >
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
  name: 'CityList',
  props: {
    cityAll: Object
  },
  data () {
    return {
      rec: ''
    }
  },
  methods: {
    handClick (e) {
      this.rec = e.target.innerText
      console.log(this.rec)
      if (this.rec) {
        const element = this.$refs[this.rec][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
    .sort-city,.a-city{
        height: .7rem;
        background-color: rgb(245,245,245);
        font-size: .244rem;
        font-weight: 400;
        line-height: .7rem;
        text-indent: .2rem;
    }
    .sort-city-ul,.a-city-ul{
        overflow: hidden;
    }
    .sort-city-li{
        width: 19.73%;
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
    .sort-city-li:nth-child(5n){
        border-right: none;
    }
    .a-city-li{
        width: 24.725%;
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
    .a-city-li:nth-child(4n){
        border-right: none;
    }
</style>
