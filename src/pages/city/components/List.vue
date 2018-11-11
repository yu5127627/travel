<template>
    <div class="city-list" ref="wrapper">
        <div>
            <div class="hot-city">热门城市</div>
            <ul class="hot-city-ul">
                <li class="hot-city-li"
                    v-for="item of hotCity"
                    v-text="item.name"
                    :key="item.id"
                ></li>
            </ul>
            <div class="sort-city">字母排序</div>
            <ul class="sort-city-ul">
                <li class="sort-city-li"
                    v-for="(sort,index) of citySort"
                    v-text="sort"
                    :key="index"
                ></li>
            </ul>
            <div class="a-city">A</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityAs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">B</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityBs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">C</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityCs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">D</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityDs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">E</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityEs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">F</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityFs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">G</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityGs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">H</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityHs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">J</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityJs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">K</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityKs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">L</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityLs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">M</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityMs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">N</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityNs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">P</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityPs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">Q</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityQs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">R</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityRs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">S</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of citySs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">T</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityBs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">W</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityWs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">X</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityXs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">Y</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityYs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
            <div class="a-city">Z</div>
            <ul class="a-city-ul">
                <li class="a-city-li"
                    v-for="city of cityZs"
                    v-text="city.name"
                    :key="city.id"
                ></li>
            </ul>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hotCity: Array,
    citySort: Array,
    cityAs: Array,
    cityBs: Array,
    cityCs: Array,
    cityDs: Array,
    cityEs: Array,
    cityFs: Array,
    cityGs: Array,
    cityHs: Array,
    cityIs: Array,
    cityJs: Array,
    cityKs: Array,
    cityLs: Array,
    cityMs: Array,
    cityNs: Array,
    cityPs: Array,
    cityQs: Array,
    cityRs: Array,
    citySs: Array,
    cityTs: Array,
    cityWs: Array,
    cityXs: Array,
    cityYs: Array,
    cityZs: Array
  },
  mounted () {
    // vue 完全加载完毕才会执行的钩子函数
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
    .city-list{
        position: absolute;
        top: 1.48rem;
        left: 0;
        right: 0;
        bottom: 0;
        overflow: hidden;
    }
    .hot-city,.sort-city,.a-city{
        height: .7rem;
        background-color: rgb(245,245,245);
        font-size: .244rem;
        font-weight: 400;
        line-height: .7rem;
        text-indent: .2rem;
    }
    .hot-city-ul,.sort-city-ul,.a-city-ul{
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
