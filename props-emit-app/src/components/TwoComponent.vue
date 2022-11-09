<template>
  <div style="width:40vw; margin:5vw">
    <h1>TwoComponent</h1>
    {{ two }}
  </div>
</template>

<script>
export default {
  name: 'TwoComponent',
  props: {
    two: String
  }
}
</script>

<style>

</style>