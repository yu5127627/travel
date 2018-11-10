<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <swiper-slide v-for="img of list" :key="img.id"  data-swiper-autoplay="2000" >
                <img class="swiper-img" :src="img.imgUrl">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        // 让轮播插件支持循环轮播
        loop: true,
        autoplay: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
    .wrapper{
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom: 26.7%;
    }
    .swiper-img{
        width: 100%;
    }
    /* 需要特殊的穿透方式才可以改变页码的颜色 */
    .wrapper >>> .swiper-pagination-bullet-active{
        background-color: #fff;
    }
</style>
