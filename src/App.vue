<template>
  <div id="app">
    <Home v-if="homeView"/>
    <AddCard v-else/>
  </div>
</template>

<script>
import Home from './views/Home'
import AddCard from './views/AddCard'

export default {
  components: {Home, AddCard},
  data(){return{
    homeView: true
  }}
};
</script>

<style>
#app {
  text-align: center;
  /* color: black; */
  margin-top: 50px;
}
</style>