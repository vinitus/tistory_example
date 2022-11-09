<template>
  <div style="width:40vw; margin:5vw">
    <h1>TwoComponent</h1>
    {{ twoData }}
  </div>
</template>

<script>
export default {
  name: 'TwoComponent',
  props: {
    // props를 통해 받은 데이터를 명시해줘야 사용할 수 있다.
    twoData: String
  }
}
</script>

<style>

</style>