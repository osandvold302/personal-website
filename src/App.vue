<template>
  <div id="app">
    <Header/>
    <About/>
    <Projects/>
    <Footer/>
  </div>
</template>

<script>
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

import Header from './components/header.vue'
import Footer from './components/footer.vue'
import About from './components/about_me_short.vue'
import Projects from './components/projects.vue'

Vue.use(BootstrapVue)

export default {
  name: 'app',
  components: {
    Header,
    About,
    Projects,
    Footer,
  }
}
</script>

<style>
html , body{
  height: 100vh;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  margin: 0 auto;
  padding: 0;
  width: 100%;
  height: 100%;
  background-color: #fffcfe;
}
</style>
