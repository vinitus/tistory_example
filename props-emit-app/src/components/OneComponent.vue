<template>
  <div style="width:40vw; margin:5vw">
    <h1>OneComponent</h1>
    <input type="text" @keyup.enter="catchInputData">
  </div>
</template>

<script>
export default {
  name: 'OneComponent',
  methods: {
    catchInputData(event) {
      // emit event 발생시키기, 받는 입장에서 HTML에서 받으니깐 kebab-case
      this.$emit('catch-in-app', event.target.value)
    }
  }
}
</script>

<style>
div div,
input {
  margin: 10px
}
</style>