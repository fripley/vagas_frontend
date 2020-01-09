<template>
  <section id="pillars" class="pillars-wrapper">
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

</style>
