<template>
  <div id="app">
    <div style="display:flex;">
      <!-- emit event를 듣는 것은 kebab-case, 호출하는 함수는 camelCase로 표기하여 호출 -->
      <one-component @catch-in-app="saveDataFromOne"></one-component>
      <!-- 그냥 문자열 형태 자체로 넘기는 것은 바인딩하지 않아도 되지만 -->
      <two-component two-data="two"></two-component>
      <!-- data나 computed 를 넘기고 싶다면 :를 통해서 바인딩 해야함 -->
      <two-component :two-data="two"></two-component>
    </div>
    <div>U input data : {{ oneInputData }}</div>
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
      oneInputData: null
    }
  },
  components: {
    OneComponent,
    TwoComponent
  },
  methods: {
    saveDataFromOne(data) {
      this.oneInputData = data
    }
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