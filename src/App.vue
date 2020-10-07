<template>
  <div id="app">
    <Navbar/>
      <Register/>
    <FooterCust/>
  </div>
</template>

<script>
import Register from './pages/Register.vue'
import Navbar from './components/Navbar'
import FooterCust from './components/FooterCust'

export default {
  name: 'App',
  components: {
    Register,
    Navbar,
    FooterCust
  }
}
</script>

<style>
@import './assets/styles/style.css'; 
@import './assets/styles/styleMobile.css'; 
@import './assets/styles/styleIpad.css'; 
@import './assets/styles/styleIpadPro.css'; 
</style>
