<template>
  <div id="app">
    <div class="container">
      <router-view/>
    </div>
    <!--<div class="homePage">
      <router-link to="/">logo</router-link>
      <router-link to="/about">About</router-link>
    </div>-->
    
  </div>
</template>
<style scoped>
@import '../src/css/container.css';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
