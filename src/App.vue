<template>
  <v-container fluid class="fundo-container">
    <div class="fundo"></div>
    <tela-login />
  </v-container>
</template>

<script setup></script>

<style>
.fundo {
  background-color: aqua;
  min-height: 100vh;
  height: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  /* Add the blur effect */
  filter: blur(8px);

  background-image: url("https://images.pexels.com/photos/32058694/pexels-photo-32058694.jpeg");
  position: relative;
  z-index: 0;
}
.fundo-container {
  overflow: hidden;
  margin: 0px;
  padding: 0px;
  width: 100vw;
  height: 100vh;
}
</style>
