<template>
  <div id="box" class="box-container">
    <slot />
  </div>
</template>

<style>
.box-container {
  box-shadow: -2px 4px 12px rgba(0, 0, 0, .2);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  flex-direction: column;
  border-radius: 12px;
}
</style>
