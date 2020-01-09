<template>
  <section id="spotlight" class="spotlight-container">
    <Title label="Marcas do app em destaque" class="mb-32" />
    <div class="spotlight-wrapper">
      <template v-for="(item, key) in business">
        <BoxLogo
          :bgColor="item.bgColor"
          :label="item.name"
          :key="key"
          class="box-logo-wrapper"
        />
      </template>
    </div>
  </section>
</template>

<script>
import Title from '~/components/atoms/title'
import BoxLogo from '~/components/molecules/box-logo'

export default {
  components: {
    BoxLogo,
    Title
  },
  props: {
    business: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style>
.spotlight-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.spotlight-wrapper {
  display: grid;
  grid-template-columns: 150px 150px 150px;
  grid-gap: 24px;
  justify-content: center;
}
@media screen and (max-width: 769px) {
  .spotlight-wrapper {
    grid-template-columns: 150px 150px;
  }
}
@media screen and (max-width: 460px) {
  .spotlight-wrapper {
    grid-template-columns: 150px;
  }
}
.box-logo-wrapper {
  padding: 16px 8px;
  width: 150px;
  height: 150px;
}
</style>
