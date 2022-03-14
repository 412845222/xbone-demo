
<template>
  <div id="css-position">
    <Scene>
      <Player></Player>
    </Scene>
  </div>
</template>

<style scoped>
#css-position {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

<script setup lang="ts">
import Scene from './components/Scene.vue'
import Player from './components/Player.vue'
</script>
