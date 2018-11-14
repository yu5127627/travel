<template>
    <div class="detail">
        <detail-banner></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list="list"></detail-list>
        </div>
    </div>
</template>

<script>
import DetailHeader from './components/Header'
import DetailBanner from './components/Banner'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [
        {
          title: '成人票',
          children: [
            {
              title: '三人团票价',
              children: [
                {title: '7:00-12:00'}
              ]
            },
            {
              title: '五人团票价',
              children: [
                {title: '2:00-6:00'}
              ]
            }
          ]
        },
        {
          title: '学生票',
          children: [
            {title: '三人团票价'},
            {title: '五人团票价'}
          ]
        },
        {
          title: '特惠票',
          children: [
            {title: '三人团票价'},
            {title: '五人团票价'}
          ]
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
    .detail{
        position: relative;
        height: 30rem;
    }
</style>
