<template>
  <div class="video-list-wrap pointer" @click="onclick">
    <li class="list-group-item video-item">
      <img class="me-3" :src="videoImgUrl" alt="video-thumbnail">
      <div class="media-body">
        {{ video.snippet.title }}
      </div>
    </li>
  </div>
</template>

<script>
export default {
  name:'VideoListItem',
  props: {
    video: Object,
  },
  methods: {
    onclick() {
      this.$emit('clicked-video', this.video)
    }
  },
  computed: {
    videoImgUrl() {
      return this.video.snippet.thumbnails.default.url
    }
  }
}
</script>

<style>
.pointer {
  cursor: pointer;
}

.pointer:hover{
  background-color: whitesmoke;
}
</style>