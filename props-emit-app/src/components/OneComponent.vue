<template>
  <div style="width:40vw; margin:5vw">
    <h1>OneComponent</h1>
    {{ one }}
  </div>
</template>

<script>
export default {
  name: 'OneComponent',
  props: {
    one: String
  }
}
</script>

<style>

</style>