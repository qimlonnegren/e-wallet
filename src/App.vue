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
@import url('https://fonts.googleapis.com/css2?family=PT+Mono&family=Source+Sans+Pro:wght@400;600;700&display=swap');
#app {
  font-family: 'PT Mono', monospace;
  text-align: center;
  width: 414px;
  height: 500px;
  margin: auto;
  padding-top: 10px;
  text-transform: uppercase;
  background-color: palevioletred;
  display: flex;
  justify-content: center;
}
h1, h6 {
  font-family: 'Source Sans Pro', sans-serif;
}

h1{
    font-weight: 700;
}
</style>