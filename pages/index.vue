<template>
  <div>
    <div>{{ count }}</div>
    <div>{{ errorMessage }}</div>
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
    const count = ref(0)
    setInterval(() => count.value++, 1000)

    const errorMessage = ref(null)
    watch(count, count => {
      if (count > 10) {
        errorMessage.value = 'Larger than 10'
      }
    })
    onUpdated(() => {
      console.log('update!!')
    })
    return {
      count,
      errorMessage
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
