<template>
  <div id="nav">
    <div class="navbar-part1">
        <router-link to="/">
            <img src="../assets/logo-tediber-text.svg" alt="tediber-logo-text">
        </router-link>    
        <router-link to="/">Nos produits <img src="../assets/stroke.png" alt="little grey stroke"></router-link>
        <router-link to="/">Le concept</router-link>
        <router-link to="/">Avis</router-link>
    </div>
    <div id="navbar-mainimage">
        <router-link to="/">
            <img src="../assets/logo-tediber.svg" alt="tediber-logo-bear">
        </router-link>    
    </div>
    <div class="navbar-part2">
        <router-link to="/">Pub tv</router-link>
        <router-link to="/">Mon compte</router-link>
        <router-link to="/">Mag</router-link>
        <router-link to="/">Contactez-nous</router-link>
        <router-link to="/">
            <img src="../assets/tediber-panier-logo.svg" alt="tediber-panier-logo">
        </router-link>    
    </div>
  </div>
</template>

<style>
#nav {
  /* border: 1px solid red; */
  display: flex;
  text-align: center;
  justify-content: center;
  align-items: center;
  height: 80px;
  box-shadow: 0 0 0.8rem 0 rgb(127 124 137 / 65%);
}

#nav a.router-link-exact-active {
  /* border: 1px solid blue; */
  color: rgb(73, 73, 73);
  text-decoration: none;
  text-transform: uppercase;
}

.navbar-part1 {
    /* border: 2px solid yellow; */
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 50vw;
    padding: 0 73px 0 20px;
}

.navbar-part2 {
    /* border: 2px solid yellow; */
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 50vw;
    padding: 0 20px 0 73px;
}

#navbar-mainimage {
    /* border: 1px solid red; */
}

</style>