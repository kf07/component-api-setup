<template>
  <form>
    TODO<br />
    <label>
      タイトル
      <input v-model="todoText.title" type="text" />
    </label>
    <label>
      メモ
      <input v-model="todoText.memo" type="text" />
    </label>
    <button type="button" @click="sendTodo">送信</button>
  </form>
</template>

<script lang="ts">
import { defineComponent, reactive } from '@vue/composition-api'
import { TodoItem } from '~/types/todoType'

export default defineComponent({
  name: 'TodoInput',
  setup(props, context) {
    const todoText: TodoItem = reactive({
      title: '',
      memo: ''
    })
    const sendTodo = () => {
      context.emit('emit-send', { title: todoText.title, memo: todoText.memo })
      todoText.title = ''
      todoText.memo = ''
    }
    return {
      sendTodo,
      todoText
    }
  }
})
</script>

<style scoped></style>
