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
    homeView: false
  }}
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=PT+Mono&family=Source+Sans+Pro:wght@400;600;700&display=swap');
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css');
#app {
  font-family: 'PT Mono', monospace;
  text-align: center;
  width: 414px;
  height: 1000px;
  margin: auto;
  padding-top: 20px;
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
  margin: auto;
  width: 200px;
  line-height: 30px;
  /* padding: 0 50px 0 50px; */
}
</style>