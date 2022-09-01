<script setup lang="ts">
import { RouterView } from "vue-router";
import NavBar from "./components/NavBar.vue";
</script>

<template>
  <link
    href="https://fonts.googleapis.com/css?family=Baloo+2:400,800&display=swap"
    rel="stylesheet"
  />
  <NavBar />
  <RouterView />
</template>

<style scoped>
</style>
