<template>
    <div>
        <div class="item" v-for="(item,index) of list" :key="index">
            <div class="item-title border-bottom">
                <span class="item-title-icon"></span>
                {{ item.title }}
            </div>
            <div v-if="item.children" class="item-children">
                <detail-list :list="item.children"></detail-list>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style scoped>
    .item-title {
        position: relative;
        font-size: .3rem;
        text-indent: .56rem;
        height: .5rem;
        line-height: .5rem;
    }
    .item-title-icon {
        position: absolute;
        width: .36rem;
        height: .36rem;
        top: .08rem;
        left: .2rem;
        background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
        margin-right: .1rem;
        background-size: .4rem 3rem;
    }
    .item-children{
        padding-left: .4rem;
    }
</style>
