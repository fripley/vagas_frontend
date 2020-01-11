<template>
  <section id="resume" class="resume-container">
    <template v-for="(item, key) in list">
      <BoxText
        :titleLabel="item.title"
        :textLabel="item.text"
        :key="key"
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

<style lang="scss">
.resume-container {
  margin: 48px 0;
}
@media screen and (min-width: 1024px) {
  .resume-container {
    grid-column: 1;
    grid-row: 1;
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: space-around;
    .text-box {
      .title-box {
        font-size: 20px;
      }
    }
  }
}
.resume-container .text-box {
  margin: 0 auto;
}
</style>
