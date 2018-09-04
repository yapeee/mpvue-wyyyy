<template>
  <div class="music-msg">
    <div class="icon"><img src=""/></div> <!--播放器指针-->
    <div class="music-image">
      <div class="icon"><img src="/static/images/timg.jpg" class="image"/></div>  <!--播放器-->
    </div>
    <div class="music-relevant">
      <div class="icon"><img src="/static/images/music-play/like.svg"/></div>
      <div class="icon"><img src="/static/images/music-play/download.svg"/></div>
      <div class="icon"><img src="/static/images/music-play/news.svg"/></div>
      <div class="icon"><img src="/static/images/music-play/relevant.svg"/></div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['text']
  }
</script>

<style scoped>
  .card {
    padding: 10px;
  }
</style>
