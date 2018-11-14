<template>
    <div class="banner">
        <img @click="handleImgClick" class="banner-img" :src="bannerImg">
        <div class="iconfont banner-icon">&#xe632;&nbsp;{{ this.gallaryImgs.length }}</div>
        <p class="banner-title">{{ sightName }}</p>
        <div class="banner-linear"></div>
        <common-gallary
                :imgs="gallaryImgs"
                v-show="showGallary"
                @close="handleGallaryClose"
        >
        </common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  components: {
    CommonGallary
  },
  methods: {
    handleImgClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
    .banner {
        /*overflow: hidden;*/
        height: 0;
        padding-bottom: 55%;

        position: relative;
    }
    .banner-img {
        width: 100%;
    }
    .banner-icon {
        width: 1.2rem;
        height: .38rem;
        line-height: .38rem;
        border-radius: .3rem;
        font-size: .24rem;
        font-weight: 500;
        background-color: rgba(0,0,0,.6);
        color: white;
        text-align: center;

        position: absolute;
        bottom: .8rem;
        left: .4rem;
    }
    .banner-title {
        position: absolute;
        bottom: .2rem;
        left: .4rem;

        font-size: .36rem;
        color: #fff;
        z-index: 1;
    }
    .banner-linear {
        position: absolute;
        bottom: 0;
        left: 0;

        width: 100%;
        height: .6rem;
        background-image: linear-gradient(to bottom,rgba(0,0,0,0),rgba(0,0,0,.7));
    }
</style>
