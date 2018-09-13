<template>
  <div class="container">
    <div class="bg-img">
      <img src="/static/images/timg.jpg" class="bg-color"/>
    </div>
    <div class="bg-img">
      <div class="mask"></div>
    </div>
    <!--content-->
    <div class="content">
      <!--title-->
      <div class="title">
        <div class="title2">
          <div class="icon"><img src="/static/images/left.svg"/></div>
          <div class="music-name">
            <div class="name h4">往后余生</div>
            <div class="player">
              <div>123</div>
              <div class="icon"><img src="/static/images/right.svg"/></div>
            </div>
          </div>
        </div>

        <div class="icon share"><img src="/static/images/music-play/share.svg"/></div>
      </div>

      <div class="change-content">
        <!--<div class="icon"><img src=""/></div> &lt;!&ndash;播放器指针&ndash;&gt;-->
        <!--<div class="music-image">-->
          <!--<div class="icon"><img src="/static/images/timg.jpg" class="image"/></div>  &lt;!&ndash;播放器&ndash;&gt;-->
        <!--</div>-->
        <!--<div class="music-relevant">-->
          <!--<div class="icon"><img src="/static/images/music-play/like.svg"/></div>-->
          <!--<div class="icon"><img src="/static/images/music-play/download.svg"/></div>-->
          <!--<div class="icon"><img src="/static/images/music-play/news.svg"/></div>-->
          <!--<div class="icon"><img src="/static/images/music-play/relevant.svg"/></div>-->
        <!--</div>-->

        <div class="volume">
        </div>
        <div class="words">
          <p>往后余生</p>
          <p>风雪是你</p>
          <p>平淡是你</p>
          <p>清贫也是你</p>
          <p>荣华是你</p>
          <p>心地温柔是你</p>
          <p>目光所致</p>
          <p class="active">也是你</p>
          <p>往后余生</p>
          <p>风雪是你</p>
          <p>平淡是你</p>
          <p>清贫也是你</p>
          <p>荣华是你</p>
          <p>心地温柔是你</p>
          <p>目光所致</p>
          <p>也是你</p>
        </div>
      </div>


      <div class="progress-bar">
        <div class="time">00:00</div>
        <div class="bar"></div>
        <div class="time">03:53</div>
      </div>

      <div class="music-switch">
        <div class="icon play-type"><img src="/static/images/music-play/single.svg"/></div>
        <div class="icon"><img src="/static/images/music-play/left.svg"/></div>
        <div class="icon play-state"><img src="/static/images/music-play/pause.svg"/></div>
        <div class="icon"><img src="/static/images/music-play/right.svg"/></div>
        <div class="icon"><img src="/static/images/music-play/menu.svg"/></div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      userInfo: {},
      title: '往后余生'
    }
  },

  components: {
  },
  created () {
  },
  methods: {
  }
}
</script>

<style scoped>
  .icon {
    width: 6vw;
    height: 6vw;
  }
  img{
    width: 100%;
    height: 100%;
  }
  .h4{
    font-size: 4vw;
    font-weight: bolder;
  }

  .bg-img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }
  .bg-img .mask {
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.5);
  }
  .bg-img .bg-color {
    -webkit-filter: blur(25px);
    -moz-filter: blur(25px);
    -o-filter: blur(25px);
    -ms-filter: blur(25px);
    filter: blur(25px);
  }
  .content{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;

    padding: 3vw;
  }
  .title {
    display: flex;
    align-items: center;
    justify-content: space-between;

    padding-bottom: 2vw;
    border-bottom: 1px #fff solid;
  }
  .title2{
    display: flex;
    align-items: center;
  }
  .title2 .music-name{
    color: #fff;
    margin-left: 3vw;
  }
  .title2 .music-name .player{
    display: flex;
    align-items: center;
    opacity: 0.6;
  }
  .title2 .music-name .player .icon {
    width: 3vw;
    height: 3vw;
  }
  .title .share {
    float: right;
  }
  .change-content {
    height: 105vw;
    overflow: scroll;
  }
  .change-content .words p{
    color: #fff;
    opacity: 0.4;
    font-size: 4vw;
    padding: 2vw;
    text-align: center;
  }
  .change-content .words .active {
    opacity: 1;
  }
  .music-image {
    display: flex;
    justify-content:center;
  }
  .music-image .icon {
    margin: 20vw 10vw 10vw 10vw;
    width: 50vw;
    height: 50vw;
    border-radius: 50vw;
    border: 6vw #000 solid;
  }
  .music-image .icon .image {
    border-radius: 50vw;
  }

  .music-relevant {
    padding: 0 20vw;
    display: flex;
    justify-content: space-between;
  }
  .progress-bar {
    padding: 3vw 0 8vw 0;
    display: flex;
    justify-content: space-between;
    color: #fff;
  }
  .progress-bar .bar {
    width: 70vw;
    margin: 2vw 0;
    background-color: rgba(255,255,255,0.2);
  }

  .music-switch {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .music-switch .play-state {
    width: 12vw;
    height: 12vw;
  }

</style>
