<template>
  <div id="app">
    <Header />
    <Skills />
    <About />
  </div>
</template>

<script>
import Header from './components/header.vue'
import Skills from './components/skills.vue'
import About from './components/about.vue'

export default {
  name: 'App',
  components: {
    Header,
    Skills,
    About
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
</style>
