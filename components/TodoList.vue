<template>
  <div>
    <ul>
      <li v-for="(todo, i) in data.list.todos" :key="i">
        {{ todo }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import {
  createComponent,
  PropType,
  onMounted,
  reactive
} from '@vue/composition-api'

const TodoList = createComponent({
  props: {
    todos: {
      type: Array as PropType<string[]>,
      required: true
    }
  },
  setup(props) {
    const data = reactive({
      list: props
    })
    return {
      data
    }
  }
})

export default TodoList
</script>

<style scoped></style>
