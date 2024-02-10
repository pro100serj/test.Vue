<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <CardVacancy
      v-for="item in listVacancy" :key="item.slug"
      :name="item.name"
      :main_technologies="item.main_technologies"
      :more_technologies="item.more_technologies"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import CardVacancy from '@/components/CardVacancy.vue'

const url = 'https://newsite.softorium.pro/admin-area/api/visitor/vacancy/';

export default {
  name: 'HomeView',
  components: {
    CardVacancy
  },

  data() {
    return {
      listVacancy: [],
    }
  },

  mounted() {
    this.getList();
  },

  methods: {
    getList() {
      this.axios.get(url).then((response) => {
        this.listVacancy = response.data;
        console.log(response.data)
      })
    }
  }
}
</script>
