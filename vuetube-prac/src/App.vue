<template>
  <div id="app">
    <h1>SSAFY TUBE</h1>
   <SearchBar
   @searched-videos = "onSearchedVideos"
   />
    <VideoDetail  :selectedVideo ="selectedVideo"/>
    <VideoList 
    
    :videos="videos" 
    @selected-video="onSelectedVideo"
    />
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import VideoDetail from './components/VideoDetail.vue';
import VideoList from './components/VideoList.vue';
export default {
  name: 'App',
  data() {
    return{
      videos: [],
      selectedVideo: {}
    }
  },
  components: {
    SearchBar,
    VideoDetail,
    VideoList,
  },
  methods: {
    onSearchedVideos(videos) {
      this.videos = videos
    },
    onSelectedVideo(selectedVideo) {
      this.selectedVideo = selectedVideo
    }
  },
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
