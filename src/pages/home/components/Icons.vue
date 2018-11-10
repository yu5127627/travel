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
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
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
