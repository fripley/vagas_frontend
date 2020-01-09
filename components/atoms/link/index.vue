<template>
  <a :class="['link-container']" :title="label" href="javascript:;">{{ label }}</a>
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
.link-container {
  color: #13bc4a;
  text-decoration: none;
  transition: color .3s;
}
.link-container:hover {
  color: rgba(19, 188, 74, .75);
}
</style>
