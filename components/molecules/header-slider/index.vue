<template>
  <div class="header-slider-container">
    <Title label="Produtos mais acessados" class="title-wrapper" />
    <Link label="Ver todos" class="link-wrapper" />
  </div>
</template>

<script>
import Title from '~/components/atoms/title'
import Link from '~/components/atoms/link'

export default {
  components: {
    Title,
    Link
  }
}
</script>

<style>
.header-slider-container {
  justify-content: space-between;
  align-items: center;
  display: grid;
  grid-template-columns: calc(80% - 52px) 20%;
  grid-column-gap: 36px;
  padding-left: 16px;
  padding-right: 16px;
}
.link-wrapper {
  justify-self: flex-end;
}
@media screen and (max-width: 460px) {
  .header-slider-container {
    grid-column-gap: 8px;
    grid-template-columns: calc(80% - 24px) 20%;
  }
}
</style>
