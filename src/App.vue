<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div class="row">
      <Course />
    </div>
  </div>
</template>

<script>
import Course from './components/Course'

export default {
  name: 'App',
  components: {
    Course
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.row{
  display: flex;
  justify-content: space-between;
  margin: 0 15%;
}
</style>
