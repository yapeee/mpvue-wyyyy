<template>
  <div class="container">
    <!--<div class="content">-->
      <!--&lt;!&ndash;title&ndash;&gt;-->
      <!--<div class="title">-->
        <!--<div class="icon"><img src="/static/images/menu_choice.svg"/></div>-->
        <!--<div class="mid-title">-->
          <!--<div class="icon"><img src="/static/images/music_choice.svg"/></div>-->
          <!--<div class="icon active"><img src="/static/images/logo_choice.svg"/></div>-->
          <!--<div class="icon"><img src="/static/images/video_choice.svg"/></div>-->
        <!--</div>-->
        <!--<div class="icon"><img src="/static/images/find_choice.svg"/></div>-->
      <!--</div>-->
      <!--&lt;!&ndash;sub title&ndash;&gt;-->
      <!--<div class="sub-title">-->
        <!--<div class="text-btn active">推荐</div>-->
        <!--<div class="text-btn">朋友</div>-->
        <!--<div class="text-btn">电台</div>-->
      <!--</div>-->
      <!--&lt;!&ndash;swiper&ndash;&gt;-->
      <!--<div class="activity-content">-->
        <!--<div class="activity-swiper">-->
          <!--<swiper indicator-dots="true" autoplay="true" interval="5000" duration="1000" circular='true'>-->
            <!--<block v-for="item in imgUrls" :key="index">-->
              <!--<swiper-item class="slide-item">-->
                <!--<image :src="item" class="slide-image" />-->
              <!--</swiper-item>-->
            <!--</block>-->
          <!--</swiper>-->
        <!--</div>-->
      <!--</div>-->
      <!--&lt;!&ndash;menu&ndash;&gt;-->
      <!--<div class="menu">-->
        <!--<div class="menu-item">-->
          <!--<div class="icon">-->
            <!--<img src="/static/images/index/radio.svg"/>-->
          <!--</div>-->
          <!--<div class="text">私人FM</div>-->
        <!--</div>-->
        <!--<div class="menu-item">-->
          <!--<div class="icon">-->
            <!--<img src="/static/images/index/calendar.svg"/>-->
          <!--</div>-->
          <!--<div class="text">每日推荐</div>-->
        <!--</div>-->
        <!--<div class="menu-item">-->
          <!--<div class="icon">-->
            <!--<img src="/static/images/index/songList.svg"/>-->
          <!--</div>-->
          <!--<div class="text">歌单</div>-->
        <!--</div>-->
        <!--<div class="menu-item">-->
          <!--<div class="icon">-->
            <!--<img src="/static/images/index/leaderboard.svg"/>-->
          <!--</div>-->
          <!--<div class="text">排行榜</div>-->
        <!--</div>-->
      <!--</div>-->
      <!--&lt;!&ndash;推荐歌单&ndash;&gt;-->
      <!--<div class="music-series">-->
        <!--<div class="tips">-->
          <!--<div class="h4">推荐歌单</div>-->
          <!--<div class="icon"><img src="/static/images/right.svg"/></div>-->
        <!--</div>-->
        <!--<div class="music-sheet">-->
          <!--&lt;!&ndash;card&ndash;&gt;-->
          <!--<div class="card">-->
            <!--<div class="card-image">-->
              <!--<div class="music-image">-->
                <!--<img src="/static/images/timg.jpg" class="bg-image"/>-->
                <!--<div class="account">-->
                  <!--<div class="icon"><img src="/static/images/index/headset.svg"/></div>-->
                  <!--<div class="text">131万</div>-->
                <!--</div>-->
              <!--</div>-->
            <!--</div>-->
            <!--<div class="text">邂逅秋意，定格美丽</div>-->
          <!--</div>-->
          <!--&lt;!&ndash;card&ndash;&gt;-->
          <!--<div class="card">-->
            <!--<div class="card-image">-->
              <!--<div class="music-image">-->
                <!--<img src="/static/images/timg.jpg"/>-->
                <!--<div class="account">-->
                  <!--<div class="icon"><img src="/static/images/index/headset.svg"/></div>-->
                  <!--<div class="text">131万</div>-->
                <!--</div>-->
              <!--</div>-->
            <!--</div>-->
            <!--<div class="text">这都是什么神仙翻唱</div>-->
          <!--</div>-->
          <!--&lt;!&ndash;card&ndash;&gt;-->
          <!--<div class="card">-->
            <!--<div class="card-image">-->
              <!--<div class="music-image">-->
                <!--<img src="/static/images/timg.jpg"/>-->
                <!--<div class="account">-->
                  <!--<div class="icon"><img src="/static/images/index/headset.svg"/></div>-->
                  <!--<div class="text">131万</div>-->
                <!--</div>-->
              <!--</div>-->
            <!--</div>-->
            <!--<div class="text">听说民谣是住进你心里的捷径</div>-->
          <!--</div>-->
        <!--</div>-->
      <!--</div>-->
    <!--</div>-->
    <!--footer-->
    <div class="play-bar">
      <div class="music-msg" @click="goToContent()">
        <div class="music-image"><img src="/static/images/timg.jpg"/></div>
        <div>
          <div>往后余生</div>
          <div class="tips">横滑可以切换上下首哦</div>
        </div>
      </div>
      <div class="options">
        <div @click="musicPlay()">
          <canvas style="width: 8vw; height: 8vw;" canvas-id="canvasid"></canvas>
        </div> <!-- 播放暂停 -->
        <div class="icon"><img src="/static/images/player-menu.svg"/></div> <!-- menu -->
      </div>
    </div>
  </div>
</template>

<script>
let context = ''
let stratNum = 1 // 起始长度
let endNum = 0 // 歌曲时长
let sAngle = 1.5 * Math.PI // 开始弧度
let eAngle = 0 // 结束弧度
let t

let isPlay = false
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
  },
  created () {
    // this.canvas()
  },
  mounted () {
    context = wx.createCanvasContext('canvasid')

    context.setStrokeStyle('#383838')
    context.setLineWidth(2)
    context.arc(12, 12, 10, 0, 2 * Math.PI, false)
    context.stroke()
    context.draw()
  },
  methods: {
    canvas () {
      let that = this
      if (stratNum <= endNum) {
        console.log('strat_num:', stratNum)
        eAngle = 2 * Math.PI / endNum + eAngle
        t = setTimeout(function () {
          context.setStrokeStyle('#DD4339')
          context.setLineWidth(2)
          context.arc(12, 12, 10, sAngle, sAngle + eAngle, false)
          context.stroke()
          context.draw()
          that.canvas()
          stratNum++
        }, 1000)
      } else {
        console.log('strat_num_end:', stratNum)
      }
    },
    musicPlay () {
      if (isPlay) { // 暂停
        this.listenerButtonPause()
        clearTimeout(t)
      } else { // 开始
        this.listenerButtonPlay()
      }
      isPlay = !isPlay
    },
    // 播放
    listenerButtonPlay () {
      let self = this
      wx.playBackgroundAudio({
        dataUrl: 'http://www.ytmp3.cn/down/51807.mp3',
        title: '雪落下的声音',
        success: function () {
          console.log('chenggong')
          setTimeout(() => {
            wx.getBackgroundAudioPlayerState({
              success: function (res) {
                console.log(123456789)
                console.log(res)
                endNum = res.duration // 选定音频的长度
                self.canvas()
              //  let status = res.status // 播放状态
              //  let dataUrl = res.dataUrl // 歌曲数据链接
              //  let currentPosition = res.currentPosition // 选定音频的播放位置
              //  let duration = res.duration // 选定音频的长度
              //  let downloadPercent = res.downloadPercent // 音频的下载进度
              },
              fail: function (res) {
                console.log(res)
              }
            })
          }, 500)
        }
      })
    },
    // 监听button暂停按钮
    listenerButtonPause () {
      wx.pauseBackgroundAudio({
      })
      console.log('暂停播放')
    },
    // 跳转
    goToContent () {
      wx.navigateTo({
        url: '/pages/music-play/main'
      })
    }
  }
}
</script>

<style scoped>
  img{
    width: 100%;
    height: 100%;
  }
  .h4{
    font-size: 5vw;
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
  .play-bar .options {
    display: flex;
    align-items: center;
  }
  .play-bar .options .icon {
    width: 6vw;
    height: 6vw;
    padding-left: 5vw;
  }
</style>
