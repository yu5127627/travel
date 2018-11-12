<template>
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
</template>

<script>
export default {
  name: 'CityHot',
  props: {
    hotCity: Array
  },
  methods: {
    handleValue (val) {
      this.$store.dispatch('changeCity', val)
      this.$router.push('/')
    }
  }
}
</script>

<style scoped>
    .hot-city{
        height: .7rem;
        background-color: rgb(245,245,245);
        font-size: .244rem;
        font-weight: 400;
        line-height: .7rem;
        text-indent: .2rem;
    }
    .hot-city-ul{
        overflow: hidden;
    }
    .hot-city-li{
        width: 33.1%;
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
    .hot-city-li:nth-child(3n){
        border-right: none;
    }
</style>
