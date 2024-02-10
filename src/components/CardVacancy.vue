<template>
  <div class="Test">
    <b>{{ name }}</b>

    <br/>
    <br/>

    Основной стек:
    <span v-for="item in main_technologies" :key="item.name">
      {{ item.name }}
    </span>
    <br/>
    <br/>
    Будет плюсом, если владеете:
    <span v-for="item in more_technologies" :key="item.name">
      {{ item.name }}
    </span>
  </div>
</template>

<script>
export default {
  name: 'CardVacancy',
  props: {
    name: String,
    main_technologies: Array,
    more_technologies: Array,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
