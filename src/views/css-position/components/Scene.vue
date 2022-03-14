<template>
  <div class="scene">
    <slot></slot>
    <img class="game_ground" src="../../../assets/img/background.png" alt="">
  </div>
</template>

<style scoped>
  .scene {
    width:960px;
    height:540px;
    border: 1px solid #fff;
    overflow: hidden;
    position: relative;
  }
  .game_ground{
    width: auto;
    height: 100%;
    
  }
</style>