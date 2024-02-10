<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="getList">Get list</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

const url = 'https://newsite.softorium.pro/admin-area/api/visitor/vacancy/';

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },

  methods: {
    getList() {
      this.axios.get(url).then((response) => {
        console.log(response.data)
      })
    }
  }
}
</script>
