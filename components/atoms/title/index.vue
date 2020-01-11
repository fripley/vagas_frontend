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
.secondary {
  font-size: 24px;
}
.tertiary {
  font-size: 18px;
}
@media screen and (max-width: 1024px) {
  .primary {
    font-size: 28px;
  }
  .secondary {
    font-size: 18px;
  }
  .tertiary {
    font-size: 16px;
  }
}
</style>
