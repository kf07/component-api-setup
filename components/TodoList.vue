<template>
  <div>
    <ul>
      <li v-for="todo in todos" :key="todo.title" class="todo-item">
        <span class="title">{{ todo.title }}</span>
        <span class="memo">{{ todo.memo }}</span>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from '@vue/composition-api'
import { TodoItem } from '~/types/todoType'

export default defineComponent({
  name: 'TodoList',
  props: {
    todos: Array as PropType<TodoItem[]>
  },
  setup(props) {
    console.log(props.todos)
  }
})
</script>

<style scoped lang="scss">
.todo-item {
  .title {
    margin-right: 20px;
  }
}
</style>
