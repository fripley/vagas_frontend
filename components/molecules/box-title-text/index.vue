<template>
  <div id="box-title-text">
    <Title :label="titleLabel" class="mb-16" />
    <Paragraph :label="textLabel" class="mb-16" />
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
