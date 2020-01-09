<template>
  <section id="resume" class="resume-container">
    <template v-for="(item, key) in list">
      <BoxText
        :titleLabel="item.title"
        :textLabel="item.text"
        :key="key"
        class="text-box align-center"
      />
    </template>
  </section>
</template>

<script>
import BoxText from '~/components/molecules/box-title-text'

export default {
  components: {
    BoxText
  },
  data () {
    return {
      list: [
        {
          title: 'Título',
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic molestias blanditiis magni praesentium repellat.'
        },
        {
          title: 'Título',
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic molestias blanditiis magni praesentium repellat.'
        },
        {
          title: 'Título',
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic molestias blanditiis magni praesentium repellat.'
        }
      ]
    }
  }
}
</script>

<style>
.resume-container {
  margin: 48px 0;
}
.text-box {
  margin: 0 auto;
  max-width: 420px;
}
.text-box:nth-child(even) {
  margin: 32px auto;
}
</style>
