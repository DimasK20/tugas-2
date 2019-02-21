<template>
  <div id="app">
    <div>
      <img src="./assets/logo.png">
    </div>
    <div>
      <router-link to="/">To Home</router-link>
      <router-link to="/Comp2">To Comp2</router-link>
      <router-link to="/Quiz">Quiz</router-link>
      <router-link to="/Quizw">Quiz</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
