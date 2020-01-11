<template>
  <div class="app-controller">
    <a href="javascript:;" title="google play">
      <img src="~/assets/google-play.png" alt="google play">
    </a>
    <a href="javascript:;" title="app store">
      <img src="~/assets/download-on-the-app-store-badge-ptbr-rgb-blk-092917.png" alt="app store">
    </a>
  </div>
</template>

<style>
.app-controller {
  display: flex;
  justify-content: space-between;
}
@media screen and (max-width: 460px) {
  .app-controller {
    flex-wrap: wrap;
    justify-content: center;
  }
  .app-controller > a:first-child {
    margin-bottom: 16px;
  }
}
</style>
