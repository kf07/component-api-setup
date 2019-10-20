<template>
  <section class="container">
    <Todo />
  </section>
</template>

<script>
import { createComponent } from '@vue/composition-api'
import Todo from '@/components/Todo.vue' // @ is an alias to /src
export default createComponent({
  components: {
    Todo
  }
})
</script>
