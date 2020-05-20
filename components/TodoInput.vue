<template>
  <form>
    TODO<br />
    <label>
      タイトル
      <input v-model="todoText.title" type="text" />
    </label>
    <label>
      メモ
      <input v-model="todoText.message" type="text" />
    </label>
    <button type="button" @click="sendTodo">送信</button>
  </form>
</template>

<script lang="ts">
import { defineComponent, reactive } from '@vue/composition-api'

export default defineComponent({
  name: 'TodoInput',
  setup(props, context) {
    const sendTodo = () => {
      console.log('test')
      context.emit('emit-send', todoText)
    }
    const todoText = reactive({
      title: '',
      message: ''
    })
    return {
      sendTodo,
      todoText
    }
  }
})
</script>

<style scoped></style>
