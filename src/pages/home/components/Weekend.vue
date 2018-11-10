<template>
    <div class="weeks">
        <div class="week-title">周末去哪儿</div>
        <ul class="week">
            <li class="week-list" v-for="item in items" :key="item.id">
                <img class="list-img" :src="item.imgUrl" alt="">
                <p class="list-title" v-text="item.title"></p>
                <p class="list-overview" v-text="item.overview"></p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      items: [
        {
          id: '01',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1509/d4/fc8b971f328b79.jpg_r_640x214_d161f3ff.jpg',
          title: '太原周边赏秋',
          overview: '秋风送爽，赏秋图绘制美丽新太原'
        },
        {
          id: '02',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1711/14/2d6405bd0868eb.jpg_r_640x214_ce59870f.jpg',
          title: '山西泡汤圣地',
          overview: '山西优质温泉大合集'
        },
        {
          id: '03',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/3b/286d0e8a9e73c5.jpg_r_640x214_142234cd.jpg',
          title: '太原必游TOP5',
          overview: '入晋的第一堂课'
        },
        {
          id: '04',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1509/82/5ef380ec1fcbf0.jpg_r_640x214_aee99250.jpg',
          title: '晋中必游TOP10',
          overview: '文化底蕴深厚，古老而活跃'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl';

    .week-title {
        font-size: .33rem;
        text-indent: 0.3rem;
        height: .5rem;
        line-height: .5rem;
        padding: .2rem 0;
        margin-top: .1rem;
        background-color: $ bgColor;
    }

    .week {
        background-color: #eee;
    }

    .week-list {
        background-color: #fff;
        margin-bottom: .1rem;
    }

    .list-img {
        height: 2.5rem;
    }

    .list-title {
        font-weight: 600;
        line-height: .6rem;
        text-indent: .2rem;
    }

    .list-overview {
        line-height: .26rem;
        font-size: .26rem;
        text-indent: .4rem;
        padding-bottom: .1rem;
    }
</style>
