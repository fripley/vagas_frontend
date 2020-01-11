<template>
  <Box class="box-wrapper">
    <template>
      <img :src="image" alt="">
      <Title :label="title" theme="secondary" />
      <Paragraph :label="text" />
    </template>
  </Box>
</template>

<script>
import Title from '~/components/atoms/title'
import Paragraph from '~/components/atoms/text'
import Box from '~/components/atoms/box'

export default {
  components: {
    Box,
    Title,
    Paragraph
  },
  props: {
    title: {
      type: String,
      default: ''
    },
    text: {
      type: String,
      default: ''
    },
    image: {
      type: String,
      default: ''
    }
  }
}
</script>

<style>
.box-wrapper {
  background-color: #fff;
  padding: 24px;
  margin: 48px auto;
  max-width: 420px;
}
@media screen and (min-width: 1024px) {
  .box-wrapper {
    margin: 0;
  }
}
.box-wrapper:first-child {
  margin-top: 0;
}
.box-wrapper:last-child {
  margin-bottom: 0;
}
.box-wrapper > p {
  font-size: 18px;
  text-align: center;
}
.box-wrapper .secondary {
  margin: 16px 0;
}
</style>
