<template>
  <div>
    <VideoListItem 
    v-for="video in videos" 
    :key="video.etag"
    :video="video"
    @clicked-video="onClickVideo"
    />
  </div>
</template>

<script>
import VideoListItem from '@/components/VideoListitem.vue'
export default {
  name:'VideoList',
  props: {
    videos : Array
  },
  components: {
    VideoListItem
  },
  methods: {
    onClickVideo(video) {
      this.$emit('selected-video', video)
    }
  }
}
</script>

<style>

</style>