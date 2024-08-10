<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HVTest',
  props: {
    value: {
      type: Number,
      required: true,
    },
  },
  emits: ['input'],
  setup(props, { emit }) {
    const handleInc = () => {
      emit('input', props.value + 1)
    }

    return {
      handleInc
    }
  },
})
</script>

<template>
  <div class="wrapper">
    <div class="value"><b>Счетчик значений:</b> {{ value }}</div>
    <button @click="handleInc">Увеличить значение</button>
  </div>
</template>

<style lang="scss">
.wrapper {
  display: flex;
  align-items: center;
  gap: 10px;
}
</style>
