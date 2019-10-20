<template>
  <div>
    <input v-model="state.text" />
    <button :class="{ on: isValid }" class="button" @click="submit">
      Add
    </button>
  </div>
</template>

<script lang="ts">
import {
  createComponent,
  reactive,
  PropType,
  computed,
  onMounted
} from '@vue/composition-api'
const TodoForm = createComponent({
  name: 'TodoForm',
  props: {
    onSubmit: {
      type: Object as PropType<(text: string) => void>,
      required: true
    }
  },
  setup(props) {
    const state = reactive({
      text: ''
    })
    const submit = () => {
      props.onSubmit(state.text)
      state.text = ''
    }
    const isValid = computed(() => state.text.length > 0)
    onMounted(() => {
      console.log(props)
    })
    return {
      isValid,
      state,
      submit
    }
  }
})

export default TodoForm
</script>
<style>
.button {
  opacity: 0.4;
}
.button.on {
  opacity: 1;
}
</style>
