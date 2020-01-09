<template>
  <section id="hero" class="hero-container">
    <AppDisclosure is-phone />
  </section>
</template>

<script>
import AppDisclosure from '~/components/molecules/app-disclosure'

export default {
  components: {
    AppDisclosure
  },
  props: {
    isReverse: {
      type: Boolean,
      default: false
    }
  }
}
</script>
