<template>
    <div class="city-sort">
        <div class="sort-city">字母排序</div>
        <ul class="sort-city-ul">
            <li class="sort-city-li"
                v-for="(sort,key) of cityAll"
                :key="key"
                :ref="key"
            >
                {{ key }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'CitySort',
  props: {
    cityAll: Object
  }
}
</script>

<style scoped>
    .sort-city{
        height: .7rem;
        background-color: rgb(245,245,245);
        font-size: .244rem;
        font-weight: 400;
        line-height: .7rem;
        text-indent: .2rem;
    }
    .sort-city-ul{
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
</style>
