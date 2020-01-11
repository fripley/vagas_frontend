<template>
  <section class="pillars-wrapper">
    <template v-for="(item, index) in pillars">
      <BoxPillar
        :title="item.title"
        :text="item.text"
        :image="item.image"
        :key="index"
      />
    </template>
  </section>
</template>

<script>
import BoxPillar from '~/components/molecules/box-pillar'

export default {
  components: {
    BoxPillar
  },
  data () {
    return {
      pillars: [
        {
          title: 'Título',
          image: require('~/assets/group-33.png'),
          text: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Officia ullam fugiat dolores eum accusantium.'
        },
        {
          title: 'Título',
          image: require('~/assets/alarm-clock-2.png'),
          text: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Officia ullam fugiat dolores eum accusantium.'
        },
        {
          title: 'Título',
          image: require('~/assets/ic-notifications-none.png'),
          text: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Officia ullam fugiat dolores eum accusantium.'
        }
      ]
    }
  }
}
</script>

<style>
@media screen and (min-width: 1024px) {
  .pillars-wrapper {
    display: grid;
    grid-template-columns: repeat(3, 30%);
    align-items: center;
    grid-column-gap: 24px;
    margin: 0 auto;
    max-width: 1024px;
  }
  .pillars-wrapper .title-container {
    font-size: 20px;
  }
  .pillars-wrapper .paragraph-container {
    font-size: 16px;
  }
  .pillars-wrapper .box-wrapper {
    padding: 64px 24px;
  }
}
</style>
