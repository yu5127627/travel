<template>
    <div class="banner">
        <img @click="handleImgClick" class="banner-img" src="http://img1.qunarzz.com/sight/p0/201402/27/9566b58bc52cbdbac547b28c48e8ec96.jpg_600x330_aaf0f175.jpg" alt="">
        <div class="iconfont banner-icon">&#xe632;&nbsp;13</div>
        <p class="banner-title">大汖温泉</p>
        <div class="banner-linear"></div>
        <common-gallary
                :imgs="imgs"
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
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/201402/27/20ad9f18716444a2f277e7eb533bfaa1.jpg_r_800x800_e6ed0dc9.jpg', 'http://img1.qunarzz.com/sight/p0/201402/27/3eab4ff7f4846d43e59936ad0f16bfd1.jpg_r_800x800_7563c335.jpg']
    }
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
