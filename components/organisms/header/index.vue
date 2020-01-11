<template>
  <header id="header" :class="['header-container', scrollY > 0 && 'scrollable']">
    <div class="header-wrapper">
      <a @click="scrollTop" href="javascript:;" title="logo" class="icon-logo">
        <img src="~/assets/group-12.png" alt="logo">
      </a>
      <ul class="user-controller">
        <li>
          <a @click="menuToggle" href="javascript:;" title="user" class="icon-user">
            <img src="~/assets/user.png" alt="User">
          </a>
        </li>
        <ul :class="['nav-account', menuSwitcher ? 'active' : '']">
          <li>
            <a href="javascript:;" title="Entrar">Entrar</a>
          </li>
          <li>|</li>
          <li>
            <a href="javascript:;" title="Criar conta">Criar conta</a>
          </li>
        </ul>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
      menuSwitcher: false,
      scrollY: 0
    }
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy () {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    menuToggle () {
      this.menuSwitcher = !this.menuSwitcher
    },
    handleScroll () {
      this.scrollY = window.scrollY
    },
    scrollTop () {
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>

<style lang="scss">
.header-container {
  width: 100%;
  overflow: hidden;
  position: fixed;
  background-color: #fff;
  margin: 0 auto;
  padding: 24px 0;
  z-index: 6;
  transition: all .3s;
  &.scrollable {
    box-shadow: 0 2px 8px rgba($color: #000000, $alpha: .3);
    padding: 18px 0;
    .icon-logo {
      max-width: 80px;
      max-height: 30px;
    }
    .icon-user {
      max-width: 16px;
      max-height: 16px;
    }
    @media screen and (min-width: 1024px) {
      .icon-logo {
        max-width: 130px;
        max-height: 50px;
      }
    }
  }
  .header-wrapper {
    margin: 0 auto;
    align-self: center;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    justify-content: center;
    align-items: center;
    grid-template-areas: "logo . controller";
    max-width: 1024px;
  }
  @media screen and (max-width: 1024px) {
    .header-wrapper {
      padding-left: 16px;
      padding-right: 16px;
    }
  }
}
@media screen and (min-width: 1024px) {
  .header-container {
    .header-wrapper {
      grid-template-areas: "logo . controller"
    }
  }
}
.user-controller .nav-account {
  position: absolute;
  top: 40px;
  right: -100px;
  transition: all .3s;
}
@media screen and (min-width: 1024px) {
  .user-controller .nav-account {
    position: static;
    display: flex;
    flex-direction: row;
    align-items: center;
    width: 160px;
    justify-content: space-between;
    margin-left: 16px;
  }
}
.user-controller .nav-account li {
  font-weight: 600;
}
.user-controller .nav-account a {
  text-decoration: none;
  color: #454344;
}
.user-controller .nav-account a:hover {
  opacity: .75;
}
.user-controller .nav-account.active {
  width: 160px;
  display: flex;
  justify-content: space-between;
  right: 0;
}
.icon-user {
  width: 24px;
  height: 24px;
  display: block;
}
@media screen and (min-width: 1024px) {
  .icon-user {
    width: 28px;
    height: 28px;
  }
}
.icon-user > img {
  width: 100%;
}
.icon-logo {
  grid-area: logo;
  justify-self: center;
  transition: max-width .3s, max-height .3s;
  max-width: 150px;
  img {
    width: 100%;
  }
}
@media screen and (min-width: 1024px) {
  .icon-logo {
    justify-self: flex-start;
    max-width: 162px;
    max-height: 64px;
  }
}
.user-controller {
  display: flex;
  grid-area: controller;
  justify-content: space-between;
  justify-self: flex-end;
  list-style: none;
  padding: 0;
  margin: 0;
  position: relative;
}
@media screen and (min-width: 1024px) {
  .user-controller {
    flex-direction: row;
  }
}
.user-controller > ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>
