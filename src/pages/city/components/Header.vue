<template>
    <div class="header">
        <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>
        </router-link>
        城市选择
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
    .header {
        height: .7rem;
        background-color: #00bcd4;
        text-align: center;
        font-size: .32rem;
        line-height: 1rem;
        color: white;
        overflow: hidden;

        position: relative;
    }
    .header-back {
        position: absolute;
        top: 0;
        left: 0;
        color: white;
        width: .64rem;
        height: .7rem;
    }
</style>
