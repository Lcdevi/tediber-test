<template>
  <NavBar />
  <router-view/>
</template>

<script>
import NavBar from './components/NavBar.vue'

export default {
  components: { NavBar }
}

</script>

<style>
@font-face {
 font-family: "Gill Sans";
 src: url("./fonts/Gill_Sans_Std_Light.woff2") format("woff2"),
        url("/fonts/Gill_Sans_Std_Regular.woff2") format("woff2");
}

#app {
  font-family: 'Gill Sans', Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

*, ::after, ::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

*:focus,*:hover {
  outline: none;
}

h3 {
  text-transform: uppercase;
}

</style>
