<template>
  <div></div>
</template>

<script lang="ts">
import { defineComponent, PropType } from '@vue/composition-api'
import { TodoItem } from '~/types/todoType'

export default defineComponent({
  name: 'TodoList',
  props: {
    todo: Object as PropType<TodoItem>
  },
  setup() {}
})
</script>

<style scoped></style>
