<template>
    <div class="header">
        <router-link
                tag="div"
                to="/"
                class="iconfont header-back"
                v-show="showVal"
        >
            &#xe624;
        </router-link>
        <div class="header-title" v-show="!showVal" :style="opacityStyle">
            <router-link
                    tag="span"
                    to="/"
                    class="iconfont header-title-back"
            >
                &#xe624;
            </router-link>
            大汖温泉
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showVal: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      console.log('scroll')
      let top = document.documentElement.scrollTop
      if (top > 46) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showVal = false
      } else {
        this.showVal = true
      }
    }
  },
  activated () {
    // 每次页面被展示时执行此钩子函数
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    // (页面即将被隐藏 / 页面即将被替换成新的页面时)被执行
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
    .header, .header-back {
        position: absolute;
    }

    .header {
        top: 0;
        left: 0;
        right: 0;
    }

    .header-back {
        top: .2rem;
        left: .2rem;

        width: .7rem;
        height: .7rem;
        color: white;
        font-size: .4rem;
        font-weight: 600;
        text-align: center;
        line-height: .7rem;
        background-color: rgba(0, 0, 0, .6);
        border-radius: .35rem;
    }

    .header-title {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: .7rem;
        line-height: .7rem;
        color: white;
        font-size: .34rem;
        text-align: center;
        background-color: #00bcd4;
    }

    .header-title-back {
        position: absolute;
        top: 0;
        left: 0;

        width: .7rem;
        height: .7rem;
    }
</style>
