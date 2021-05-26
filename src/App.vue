<template>
 <NavBar/>
 <Content/>
</template>

<script>
import Content from './components/Content.vue'
import NavBar from "./components/NavBar"
export default {
  name: 'App',
  components: {
    NavBar,
    Content
  }
}

</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin:0;
  display: flex;
  flex-direction: column;
  background-color: aqua;
  height: 100vh;
  
}
body{
  height: 100vh;
  margin: 0;
  padding: 0;
}
</style>
