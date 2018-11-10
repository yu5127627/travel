<template>
    <div class="rm">
        <div class="rm-title">
            <span class="iconfont">&#xe627;</span>
            猜你喜欢
        </div>
        <ul class="rm-like">
            <li class="rm-like-list border-bottom" v-for="list in lists" :key="list.id">
                <img class="rm-like-img" :src="list.imgUrl" :alt="list.title">
                <div class="rm-list-info">
                    <p class="rm-list-info-title" v-text="list.title"></p>
                    <p class="rm-list-info-content" v-text="list.content"></p>
                    <p class="rm-list-info-address">
                        <span v-text="list.address"></span>
                        <button class="rm-list-info-btn" v-text="list.click"></button>
                    </p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      lists: [
        {
          id: '01',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201402/27/9566b58bc52cbdbac547b28c48e8ec96.jpg_200x200_d565de35.jpg',
          title: '大汖温泉',
          content: '将名贵中草药加入温泉水中，具有强身健体的神奇功效，被视为养生圣品。',
          address: '迎泽区',
          click: '查看详情'
        },
        {
          id: '02',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1601/7d/7d5ba85cdaeee83a90.img.jpg_200x200_233cac4a.jpg',
          title: '台骀山滑世界',
          content: '滑世界体验乐园的以“体验”为理念，依据地形，打造以“滑”类活动为主体娱乐项目，以挖掘中发现的“龙龟”雏形为底蕴，复原加深其韵义，使其成为滑世界入口的标志性景观。',
          address: '迎泽区',
          click: '查看详情'
        },
        {
          id: '03',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201402/11/dfcd923ef9a49c9a524b8c9b7869aeca.jpg_200x200_e7c0125b.jpg',
          title: '东湖醋园',
          content: '进入古色古香的美和居醋坊，犹如来到了500年前的老陈醋作坊，老醋芳香、扑鼻沁心，醋味十足，难以忘怀。',
          address: '杏花岭区',
          click: '查看详情'
        },
        {
          id: '04',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201305/31/5d45aefbe558d610c8d65eac.jpg_200x200_72b81ed8.jpg',
          title: '山西晋祠博物馆',
          content: '晋祠是祭祀西周唐国诸侯姬虞的祠堂，创建于西周（公元前11世纪）。',
          address: '晋源区',
          click: '查看详情'
        },
        {
          id: '05',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1711/eb/eb78eca5fe929dd2a3.img.jpg_200x200_0c0582ae.jpg',
          title: '太原华宇百花谷',
          content: '太原华宇百花谷商业中心规划的体量、业态、功能、品质、体验在未来十五年内都将领先同业，首屈一指。',
          address: '小店区',
          click: '查看详情'
        }
      ]
    }
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
