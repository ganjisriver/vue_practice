<template>
  <div>
    <div class="ratio ratio-16x9">
      <iframe :src="videoSrc" frameborder="0"></iframe>
    </div>
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">{{selectedVideo.snippet.title}}</h5>
        <p class="card-text">{{selectedVideo.snippet.description}}</p>
  </div>
</div>
  </div>
</template>

<script>
export default {
  name:'VideoDetail',
  props: {
    selectedVideo: Object
  },
  computed: {
    videoSrc() {
      return `https://www.youtube.com/embed/${this.selectedVideo.id.videoId}`
    }
  },
  
}
</script>

<style>

</style>