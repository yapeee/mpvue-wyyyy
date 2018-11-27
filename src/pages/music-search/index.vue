<template>
  <div class="container">
    <div class="content">
      <!--search-->
      <!--推荐-->
      <!--历史记录-->
    </div>
    <!--footer-->
    <div class="play-bar">
      <div class="music-msg">
        <div class="music-image"><img src="/static/images/timg.jpg"/></div>
        <div>
          <div>往后余生</div>
          <div class="tips">横滑可以切换上下首哦</div>
        </div>
      </div>
      <div>
        <div><img src=""/></div> <!-- 播放暂停 -->
        <div><img src=""/></div> <!-- menu -->
      </div>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      userInfo: {},
      imgUrls: [
        '/static/images/index/swiper-1.jpg',
        '/static/images/index/swiper-2.jpg',
        '/static/images/index/swiper-3.jpg'
      ]
    }
  },

  components: {
    card
  },
  created () {
  },
  methods: {
  }
}
</script>

<style scoped>
  img{
    width: 100%;
    height: 100%;
  }
  .h4{
    font-size: 4vw;
    font-weight: bolder;
  }
  .content {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 12vw;
    overflow: scroll;
  }
  .title {
    background-color: #DD4339;
    padding: 3vw;

    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .title .icon {
    width: 6vw;
    height: 6vw;
    opacity: 0.5;
  }
  .title .icon.active {
    opacity: 1;
  }
  .title .mid-title {
    width: 30vw;
    display: flex;
    justify-content: space-between;
  }
  .sub-title{
    background-color: #DD4339;
    padding: 3vw 10vw;
    color: #fff;

    display: flex;
    justify-content: space-between;
  }
  .sub-title .text-btn{
    padding-bottom: 1vw;
    opacity: 0.5;
  }
  .sub-title .text-btn.active {
    border-bottom: 1vw #fff solid;
    opacity: 1;
  }
  .activity-content {
    background-color: #DD4339;
  }
  .activity-content .activity-swiper {
    height: 30vw;
    padding: 0 2vw;
    margin-bottom: 15vw;
  }
  .activity-content .activity-swiper .slide-item {
    border-radius: 2vw;
  }
  .menu {
    padding: 5vw;

    display: flex;
    justify-content: space-between;
  }
  .menu .menu-item {

  }
  .menu .menu-item .text {
    text-align: center;
  }
  .menu .menu-item .icon {
    border-radius: 50vw;
    background-color: #DD4339;
    width: 8vw;
    height: 8vw;
    padding: 4vw;
    margin: 1vw;
  }

  .music-series {
    padding: 0 2vw;
  }
  .music-series .tips {
    display: flex;
    align-items: center;
  }
  .music-series .tips .icon {
    width: 5vw;
    height: 5vw;
  }
  .music-sheet {
    display: flex;
    margin: 0 -1vw;
  }
  .card {
    width: 33%;
    margin: 3vw 1vw;
    position: relative;
  }
  .card .card-image{
    height: 30vw;
  }
  .card .account {
    position: absolute;
    top: 0;
    right: 0;
    /*left: 0;*/
    /*background: linear-gradient(to right, rgba(255,255,255,0) , rgba(255,255,255,1));*/
    display: flex;
    justify-content: flex-end;
    color: #fff;
  }
  .card .account .icon {
    width: 3vw;
    height: 3vw;
  }

  .card .music-image{
    width: 30vw;
    height: 30vw;
  }
  .play-bar {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 10vw;
    padding: 1vw 3vw;
    box-shadow:0 -1px 5px #eee;
    background-color: #fff;

    display: flex;
    justify-content: space-between;
  }
  .play-bar .music-msg {
    display: flex;
    align-items: center;
  }
  .play-bar .music-image {
    width: 8vw;
    height: 8vw;
    padding-right: 2vw;
  }
  .play-bar .music-msg .tips {
    color: #bbb;
  }
</style>
