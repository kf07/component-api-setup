<template>
  <section class="container">
    <Todo />
  </section>
</template>

<script lang="ts">
import Todo from '~/components/Todo.vue'
export default {
  components: {
    Todo
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
}
</style>
