<template>
    <div class="weeks">
        <div class="week-title">周末去哪儿</div>
        <ul class="week">
            <li class="week-list" v-for="item in list" :key="item.id">
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
  props: {
    list: Array
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
        background-color: $bgColor;
    }

    .week {
        background-color: #eee;
    }

    .week-list {
        background-color: #fff;
        margin-bottom: .1rem;
    }

    .list-img {
        width: 100%;
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
