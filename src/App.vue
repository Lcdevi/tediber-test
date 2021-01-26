<template>
  <div id="nav">
    <!-- <router-link to="/">Home</router-link> | -->
    <router-link to="/">Nos produits</router-link>
    <router-link to="/">Le concept</router-link>
    <router-link to="/">Avis</router-link>
    <router-link to="/">Pub tv</router-link>
    <router-link to="/">Mon compte</router-link>
    <router-link to="/">Mag</router-link>
    <router-link to="/">Contactez-nous</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: rgb(73, 73, 73);
  text-decoration: none;
}
</style>
