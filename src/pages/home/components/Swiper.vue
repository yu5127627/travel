<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="img of swiperList" :key="img.id"  data-swiper-autoplay="2000" >
                <img class="swiper-img" :src="img.imgUrl">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        // 让轮播插件支持循环轮播
        loop: true,
        autoplay: true
      },
      swiperList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/31/da037478f37cf202.jpg_750x200_a02cf862.jpg'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/12/856f100069809e02.jpg_750x200_e3485a2b.jpg'
        },
        {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/70/5603e6a535062402.jpg_750x200_2c552f2c.jpg'
        },
        {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg'
        },
        {
          id: '005',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/1c/4847ea66072c7b02.jpg_750x200_c32457fb.jpg'
        }
      ]
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
