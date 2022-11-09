### props와 emit에 대한 pjt

```js
// src/App.vue
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
```

---

```js
// src/components/OneComponent.vue
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
```

---

```js
// src/components/TwoComponent.vue
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
```
