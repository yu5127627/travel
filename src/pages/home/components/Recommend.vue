<template>
    <div class="rm">
        <div class="rm-title">
            <span class="iconfont">&#xe627;</span>
            猜你喜欢
        </div>
        <ul class="rm-like">
            <router-link
                tag="li"
                class="rm-like-list border-bottom"
                v-for="item in list"
                :key="item.id"
                to="detail/ + item.id"
            >
                <img class="rm-like-img" :src="item.imgUrl" :alt="item.title">
                <div class="rm-list-info">
                    <p class="rm-list-info-title" v-text="item.title"></p>
                    <p class="rm-list-info-content" v-text="item.content"></p>
                    <p class="rm-list-info-address">
                        <span v-text="item.address"></span>
                        <button class="rm-list-info-btn" v-text="item.click"></button>
                    </p>
                </div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    .rm-title{
        font-size: .33rem;
        text-indent: 0.3rem;
        height: .5rem;
        line-height: .5rem;
        padding: .2rem 0;
        margin-top: .1rem;
        background-color: $bgColor;
    }
    .rm-like-list{
        display: flex;
        height: 2rem;
        overflow: hidden;
        padding: .2rem;
        letter-spacing: .02rem;
    }
    .rm-like-img{
        width: 2rem;
        height: 2rem;
    }
    .rm-list-info{
        margin-left: .2rem;
    }
    .rm-list-info-title{
        font-size: .3rem;
        font-weight: 600;
        padding-bottom: .1rem;
        line-height: .4rem;
    }
    .rm-list-info-content{
        height: .9rem;
        font-size: .26rem;
        line-height: .30rem;
        margin-bottom: .2rem;
        display: -webkit-box;
        overflow: hidden;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 3;
    }
    .rm-list-info-address{
        color: rgba(255,130,0,.9);
        font-weight: 600;
        font-size: .32rem;
        line-height: .4rem;
    }
    .rm-list-info-btn{
        background-color: rgba(110,111,255,.8);
        color: white;
        padding: .01rem;
        border-radius: .06rem;
        margin-left: .3rem;
        font-size: .26rem;
    }
</style>
