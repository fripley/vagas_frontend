<template>
  <button :class="['button', theme]" @click="$emit('onClick', this)" type="button">
    {{ label }}
  </button>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    theme: {
      type: String,
      default: 'primary'
    }
  }
}
</script>
