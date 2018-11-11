<template>
    <div class="city-search">
        <div class="search">
            <span class="ch-in active">境内</span>
            <span class="ch-out">境外/港澳台</span>
        </div>
    </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
    .city-search {
        height: .4rem;
        background-color: #00bcd4;
        padding: .2rem;
        margin-top: -.02rem;
    }
    .search {
        height: .4rem;
        width: 5.48rem;
        margin: 0 auto;
        border: 1px solid #fff;
        border-radius: .03rem;
        overflow: hidden;
    }
    .active{
        background-color: #fff !important;
        color: #00bcd4 !important;
    }
    .ch-in,.ch-out{
        width: 2.7rem;
        height: .4rem;
        line-height: .4rem;
        display: inline-block;
        text-align: center;
        background-color: #00bcd4;
        color: #fff;
        overflow: hidden;
    }
</style>
