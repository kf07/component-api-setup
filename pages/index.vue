<template>
  <div>
    <button @click="increment">inc</button>
    <div>Count is: {{ state.count }}, double is: {{ state.double }}</div>
    <input v-model="state.message" type="text" />
    <div>{{ state.message }}</div>
    <div>{{ double }}</div>
    <div>{{ count }}</div>
    <div>{{ message }}</div>
    <div>{{ upperMessage }}</div>
    <div>
      <div><input v-model.number="numbers.num1" type="number" /></div>
      <div><input v-model.number="numbers.num2" type="number" /></div>
      <div>{{ numbers.totalNumber }}</div>
      <div>{{ countRef }}</div>
      <div>{{ countPlusOneRef }}</div>
    </div>
  </div>
</template>

<script>
import {
  createComponent,
  reactive,
  computed,
  watch,
  onUpdated,
  ref
} from '@vue/composition-api'

export default createComponent({
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2),
      message: 'input message'
    })
    const countRef = ref(0)
    const countPlusOneRef = computed(() => countRef.value + 1)
    countRef.value = 5
    const numbers = reactive({
      num1: 0,
      num2: 0,
      totalNumber: computed(() => numbers.num1 + numbers.num2)
    })
    const count = ref(0)
    const message = ref('The quick brown fox jumps over the lazy dog')
    const upperMessage = message.value.toUpperCase()
    console.log(upperMessage)

    count.value++
    console.log(count.value) // 1
    const double = computed(() => state.count * 2)
    function increment() {
      state.count++
    }
    onUpdated(() => {
      console.log('updated')
    })

    return {
      countRef,
      countPlusOneRef,
      numbers,
      upperMessage,
      message,
      count,
      state,
      double,
      increment
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
