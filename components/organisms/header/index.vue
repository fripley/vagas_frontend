<template>
  <header id="header" class="header-container">
    <a href="javascript:;" title="logo" class="icon-logo">
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
  </header>
</template>

<script>
export default {
  data () {
    return {
      menuSwitcher: false
    }
  },
  methods: {
    menuToggle () {
      this.menuSwitcher = !this.menuSwitcher
    }
  }
}
</script>

<style>
.header-container {
  width: 100%;
  display: grid;
  max-width: 600px;
  grid-template-columns: 1fr 1fr 1fr;
  justify-content: center;
  align-items: center;
  margin: 24px auto;
  grid-template-areas: ". logo controller";
  overflow: hidden;
  padding-bottom: 10px;
}
@media screen and (min-width: 1024px) {
  .header-container {
    max-width: 100%;
    grid-template-areas: "logo . controller"
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
  width: 32px;
  height: 32px;
  display: block;
}
@media screen and (min-width: 1024px) {
  .icon-user {
    width: 24px;
    height: 24px;
  }
}
.icon-user > img {
  width: 100%;
}
.icon-logo {
  grid-area: logo;
  justify-self: center;
}
@media screen and (min-width: 1024px) {
  .icon-logo {
    justify-self: flex-start;
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
