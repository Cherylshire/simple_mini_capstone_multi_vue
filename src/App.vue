<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Tis da home page'</router-link> ← ☼ →
      <router-link to="/test">Jus' testing</router-link> ← ☼ →
      <router-link to="/products/index">PRODUCTS are Here</router-link> ← ☼ →
      <router-link to="/products/new">New Product you Fancy</router-link>

    </div>
    <router-view/>
    <!-- "router-view/" router.js, a place holder for the entire home page, holds all individual pages -->
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
