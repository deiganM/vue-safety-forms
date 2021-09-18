<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link :to="{ name: 'About' }">About</router-link>
      <router-link :to="{ name: 'RiskMatrix' }">Risk Matrix</router-link>
    </div>
    <router-view/>
  </div>
</template>


<style>

@import url('https://fonts.googleapis.com/css2?family=Open+Sans&family=Roboto&display=swap');

body {
  margin: 0;
}

#app {
  font-family: 'Roboto', Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

#nav {
  display: flex;
  justify-content: center;

  margin: 0;
  padding: 0;
  height: 10vh;
  width: 100vw;
  background: mediumspringgreen;
}

#nav a {
  margin: 2rem;
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
