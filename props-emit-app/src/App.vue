<template>
  <div id="app" style="display:flex;">
    <one-component one="1"></one-component>
    <two-component :two="two"></two-component>
    <two-component two="two"></two-component>
  </div>
</template>

<script>
import OneComponent from './components/OneComponent.vue'
import TwoComponent from './components/TwoComponent.vue'

export default {
  name: 'App',
  data() {
    return {
      two: '2',
    }
  },
  components: {
    OneComponent,
    TwoComponent
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
