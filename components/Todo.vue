<template>
  <div>
    <TodoInput @emit-send="todoAdd" />
    <TodoList />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, watchEffect } from '@vue/composition-api'
import TodoList, { TodoItem } from './TodoList.vue'
import TodoInput from '~/components/TodoInput.vue'

export interface TodoData {
  todos: TodoItem[]
}
export default defineComponent({
  name: 'Todo',
  components: { TodoInput, TodoList },
  setup() {
    const state: TodoData = reactive({
      todos: []
    })
    const todoAdd = (todos: TodoItem) => {
      state.todos.push(todos)
    }
    watchEffect(() => console.log(state.todos))
    return {
      todoAdd
    }
  }
})
</script>

<style scoped></style>
