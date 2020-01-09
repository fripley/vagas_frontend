<template>
  <h1 :class="[theme, 'title-container']">
    {{ label }}
  </h1>
</template>

<script>
export default {
  props: {
    theme: {
      type: String,
      default: 'primary'
    },
    label: {
      type: String,
      default: 'Lorem'
    }
  }
}
</script>

<style>
.title-container {
  letter-spacing: 1px;
}
.primary {
  font-size: 32px;
}
/* .secondary {} */
.tertiary {
  font-size: 18px;
}
</style>
