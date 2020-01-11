<template>
  <section id="spotlight" class="spotlight-container">
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
import BoxLogo from '~/components/molecules/box-logo'

export default {
  components: {
    BoxLogo
  },
  props: {
    business: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style lang="scss">
.spotlight-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
@media screen and (min-width: 1024px) {
  .spotlight-container {
    grid-column: 2;
    grid-row: 1;
  }
}
.spotlight-wrapper {
  display: grid;
  grid-template-columns: 150px 150px 150px;
  grid-gap: 24px;
  justify-content: center;
  .box-container {
    &:nth-child(n+12) {
      &:nth-child(-n+16) {
        display: none;
      }
    }
    &:last-child {
      display: none;
    }
    &:nth-child(5n) {
      display: none;
    }
  }
}
@media screen and (min-width: 1024px) {
  .spotlight-wrapper {
    grid-template-columns: repeat(4, 110px);
    .box-container {
      &:nth-child(n+12) {
        &:nth-child(-n+16) {
          display: flex;
        }
      }
      &:last-child {
        display: flex;
      }
      &:nth-child(5n) {
        display: flex;
      }
    }
  }
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
@media screen and (min-width: 1024px) {
  .box-logo-wrapper {
    padding: 16px 0 8px;
    width: 110px;
    height: 110px;
    width: 100%;
  }
}
</style>
