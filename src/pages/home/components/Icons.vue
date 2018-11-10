<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page,index) in pages" :key="index" data-swiper-autoplay="5000">
                <div class="icon" v-for="item in page" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src="item.imgUrl">
                    </div>
                    <p class="icon-title" v-text="item.title"></p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      items: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          title: '景点门票'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          title: '一日游'
        },
        {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          title: '名胜古迹'
        },
        {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          title: '必游榜单'
        },
        {
          id: '005',
          imgUrl: 'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          title: '打卡圣地'
        },
        {
          id: '006',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          title: '平遥古城'
        },
        {
          id: '007',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
          title: '五台山'
        },
        {
          id: '008',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
          title: '王家大院'
        },
        {
          id: '009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
          title: '乔家大院'
        },
        {
          id: '010',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
          title: '全部玩乐'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.items.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
    .icons{
        width: 100%;
        height: 0;
        padding-bottom: 50%;
        overflow: hidden;
    }
    .icon{
        overflow: hidden;
        width: 25%;
        height: 0;
        padding-bottom: 25%;
        float: left;

        position: relative;
    }
    .icon-img{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: .44rem;
        box-sizing: border-box;
        padding: .15rem;
    }
    .icon-img-content{
        height: 100%;
        display: block;
        margin: 0 auto;

    }
    .icon-title{
        height: .44rem;
        line-height: .44rem;
        text-align: center;

        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
    }
</style>
