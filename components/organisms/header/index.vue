<template>
  <header id="header" class="header-container">
    <a href="javascript:;" title="logo" class="icon-logo">
      <img src="~/assets/group-12.png" alt="logo">
    </a>
    <ul class="user-controller">
      <li>
        <a href="javascript:;" title="user" class="icon-user">
          <img src="~/assets/user.png" alt="User">
        </a>
      </li>
      <li class="desktop-only">
        <a href="javascript:;" title="Entrar">Entrar</a>
      </li>
      <li class="desktop-only">
        <a href="javascript:;" title="Criar conta">Criar conta</a>
      </li>
    </ul>
  </header>
</template>

<style>
.header-container {
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-content: center;
  align-items: center;
  margin: 24px auto;
  grid-template-areas: ". logo controller";
}
/* .icon-user { } */
.icon-logo {
  grid-area: logo;
  justify-self: center;
}
.user-controller {
  display: flex;
  grid-area: controller;
  justify-content: space-between;
  justify-self: flex-end;
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>
