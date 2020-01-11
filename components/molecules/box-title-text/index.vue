<template>
  <div class="text-box">
    <Title :label="titleLabel" class="title-box mb-16" />
    <Paragraph :label="textLabel" class="paragraph-box mb-16" />
  </div>
</template>

<script>
import Title from '~/components/atoms/title'
import Paragraph from '~/components/atoms/text'

export default {
  components: {
    Title,
    Paragraph
  },
  props: {
    titleLabel: {
      type: String,
      default: ''
    },
    textLabel: {
      type: String,
      default: ''
    },
    subtitle: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style>
.text-box {
  margin: 0;
  max-width: 420px;
  text-align: center;
}
.text-box:nth-child(even) {
  margin: 32px auto;
}
@media screen and (min-width: 1024px) {
  .paragraph-box,
  .title-box {
    text-align: left;
    text-align: left;
  }
  /* .paragraph-box {} */
}
</style>
