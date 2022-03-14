<template>
  <div class="scene">
    <slot></slot>
    <img class="scene_img" src="../../../assets/img/background.png" alt="" />
  </div>
</template>

<style scoped>
.scene {
  width: 960px;
  height: 540px;
  border: 1px solid #fff;
  overflow: hidden;
  position: relative;
}
.scene_img {
  height: 100%;
}
</style>
