<template>
  <div id="app">
    <component :is="layout">
      <router-view :currentLayout.sync="layout"/>
    </component>
  </div>
</template>
<script>
export default {
  data() {
    return {
      layout: () => import(/* webpackChunkName: "defaultlayout" */ './layouts/default.vue') 
    }
  }
}
</script>
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
