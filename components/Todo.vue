<template>
  <div class="todo">
    <TodoInput @emit-send="todoAdd" />
    <TodoList :todos="state.todos" />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, watchEffect } from '@vue/composition-api'
import TodoList from './TodoList.vue'
import TodoInput from '~/components/TodoInput.vue'
import { TodoItem, TodoData } from '@/types/TodoType'

export default defineComponent({
  name: 'Todo',
  components: { TodoInput, TodoList },
  setup() {
    const state: TodoData = reactive({
      todos: []
    })
    const todoAdd = (todos: TodoItem) => {
      console.log(todos)
      state.todos.push(todos)
    }
    watchEffect(() => console.log(state.todos))
    return {
      todoAdd,
      state
    }
  }
})
</script>

<style scoped>
.todo {
  margin-top: 60px;
}
</style>
