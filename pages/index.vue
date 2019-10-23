<template>
  <section class="container">
    <div>
      <div>{{ state.count }}</div>
      <button @click="countPlus">たす</button>
    </div>
  </section>
</template>

<script>
import { createComponent, computed, reactive } from '@vue/composition-api'
import addCount from '~/use/addCount'

export default createComponent({
  setup() {
    const state = reactive({
      count: 0
    })
    // const add = addCount()
    const countPlus = () => {
      state.count = addCount(state.count)
    }
    return {
      state,
      countPlus
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
