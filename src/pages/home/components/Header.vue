<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-center">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to="/city">
            <div class="header-right">
                {{ this.$store.state.city }}
                <span class="iconfont search-icon">&#xe6aa;</span>
            </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl';

    .header {
        height: .86rem;
        line-height: .86rem;
        background-color: $bgColor;
        color: #fff;

        display: flex;
    }

    .header-left {
        width: .64rem;
        float: left;
    }

    .back-icon {
        text-align: center;
        font-size: .4rem;
    }

    .header-center {
        height: .64rem;
        line-height: .64rem;
        background-color: #fff;
        border-radius: .1rem;
        margin: .12rem 0 0 .2rem;
        padding-left: .2rem;
        color: #ccc;

        flex: 1;
    }

    .header-right {
        min-width: 1.04rem;
        padding: 0 .1rem;
        float: right;
        text-align: center;
        color: #fff;
        overflow: hidden;
    }

    .search-icon {
        font-size: .24rem;
        margin-left: -.1rem;
    }
</style>
