<script setup lang="ts">
import { RouterLink } from "vue-router";
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">App</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>
</template>

<style lang="scss">
@import "../assets/colours.scss";

nav {
  font-size: 1rem;
  text-align: center;
  margin-top: 1rem;
}

nav a {
  padding: 0 1rem;
  border-left: 1px solid $colour-primary-light;
  font-weight: 600;
}

nav a.router-link-exact-active {
  color: $colour-primary;
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a:first-of-type {
  border: 0;
}
</style>
