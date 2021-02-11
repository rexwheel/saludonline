<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/clientes">Clientes</router-link> |
       <router-link to="/negocio">Negocios</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
body{
  margin: 0px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #f9f9f9;
}

#nav {
  padding: 20px;
  background-color: #000;
  margin: 0px;
}

#nav a {
  font-weight: bold;
  color: #fff;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: #fbff00;
}
</style>
