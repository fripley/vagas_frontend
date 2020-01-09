<template>
  <Box :style="'background-color: ' + bgColor">
    <img src="~/assets/logo-placeholder-2-x.png" alt="logo">
    <Paragraph :label="label" theme="secondary" class="align-center mt-16" />
  </Box>
</template>

<script>
import Box from '~/components/atoms/box'
import Paragraph from '~/components/atoms/text'

export default {
  components: {
    Box,
    Paragraph
  },
  props: {
    bgColor: {
      type: String,
      default: '#fff'
    },
    label: {
      type: String,
      default: ''
    }
  }
}
</script>
