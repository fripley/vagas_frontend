<template>
  <p id="paragraph" class="paragraph-container">
    {{ label }}
  </p>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    }
  }
}
</script>

<style>
.paragraph-container {
  font-size: 18px;
  letter-spacing: 1px;
}
</style>
