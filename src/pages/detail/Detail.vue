<template>
    <div class="detail">
        <detail-banner></detail-banner>
        <detail-header></detail-header>
    </div>
</template>

<script>
import DetailHeader from './components/Header'
import DetailBanner from './components/Banner'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader
  }
}
</script>

<style lang="stylus" scoped>
    .detail{
        position: relative;
        height: 30rem;
    }
</style>
