<template>
  <div class="mb-2">
    <input type="text" @input="onInput" @keyup.enter="onChange">
    <button class="ms-2 btn btn-primary" @click="onChange">검색</button>
  </div>
</template>

<script>
import axios from 'axios'
const URL = 'https://www.googleapis.com/youtube/v3/search'
const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY

export default {
  name:'SearchBar',
  data() {
    return {
      query: '',
    }
  },
  methods: {
    onInput(event) {
      this.query = event.target.value
    },
    onChange() {
      axios.get(URL, {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: this.query
        }
      })
      .then(res => {
        this.$emit('searched-videos', res.data.items)
      })
      .catch(err => console.error(err))
      
    }
  }
}
</script>

<style>

</style>