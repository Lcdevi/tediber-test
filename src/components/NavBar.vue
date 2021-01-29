<template>
  <div id="nav">
    <div class="navbar-part0">
        <div class="barres-menu"></div>
    </div>
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
  border: 1px solid yellow;
  display: flex;
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
    padding: 0 70px 0 20px;
}

.navbar-part2 {
    /* border: 2px solid yellow; */
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 50vw;
    padding: 0 20px 0 70px;
}

/* ------- BURGER MENU --------*/
.navbar-part0 {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  display: none;
  width: 100vw;
  /* border: 1px solid yellow; */
}
.barres-menu {
  width: 21px;
  height: 2.2px;
  background-color: #202447;
  border-radius: 4px;
  margin: 0 0 0 28px;
}
.barres-menu::before,
.barres-menu::after {
  content: '';
  position: absolute;
  width: 21px;
  height: 2.2px;
  background-color: #202447;
  border-radius: 5px;
}
.barres-menu::after {
  transform: translateY(-6.5px);
}
.barres-menu::before {
  transform: translateY(6.5px);
}


/* ------- RESPONSIVE DESIGN POUR < 765 (IPAD) -------- */
@media (max-width: 765px) {
    
    
    #navbar-mainimage {
        display: none;
    }
    .navbar-part1 a:nth-child(1n+2) {
        display: none;
    }
    .navbar-part2 a:nth-child(-1n+4) {
        display: none;
    }
    .navbar-part0 {
        display: block;
    }
    .navbar-part1 {
        padding: 0;
        display: flex;
        justify-content: center;
        width: 100vw;
    }
    .navbar-part2 {
        padding: 0;
        width: 100vw;
        display: flex;
        justify-content: flex-end;
    }
    .navbar-part2 img {
        margin: 0 22px 0 0;
    }
}

/* ------- RESPONSIVE DESIGN POUR IPAD - BREAKPOINT A 1113 -------- */

@media (max-width: 1113px) {
    #navbar-mainimage {
      display: none;
    }
    .navbar-part1 {
      padding: 0 10px 0 10px;
      font-size: 12px;
    }
      .navbar-part2 {
      padding: 0 10px 0 10px;
      font-size: 12px;
    }
}


</style>