<template>
  <div>
    <TodoForm :on-submit="putTodo" />
    <TodoList :todos="state.todos" />
  </div>
</template>

<script lang="ts">
import { createComponent, reactive } from '@vue/composition-api'
import TodoList from '@/components/TodoList.vue'
import TodoForm from '@/components/TodoForm.vue'
const Todo = createComponent({
  components: {
    TodoList,
    TodoForm
  },
  setup() {
    const state = reactive({
      todos: [] as string[]
    })
    const putTodo = (todo: string) => {
      state.todos.push(todo)
    }
    return {
      state,
      putTodo
    }
  }
})
export default Todo
</script>

<style scoped></style>
