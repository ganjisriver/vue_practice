<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="toHome">홈으로!</button>
    <input type="text" 
      @keyup.enter="toHello"
      v-model="inputData"
    >
  </div>
</template>

<script>
export default {
  name:  'AbboutView',
  data() {
    return {
      inputData: null,
    } 
  },
  methods: {
    toHome() {
      this.$router.push({ name: 'home'})
    },
    toHello() {
      this.$router.push({name: 'hello', params: { userName: this.inputData}})
      // this.$router.push({ path:`hello/${this.inputData}`} )
    }
  }
}
</script>