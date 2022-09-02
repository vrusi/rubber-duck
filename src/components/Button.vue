<script setup lang="ts">
const msg = "What am I doing wrong?";
</script>

<template>
  <button role="button">{{ msg }}</button>
</template>

<style lang="scss">
@import "../assets/colours.scss";

button {
  align-items: center;
  appearance: none;
  background-color: $color-a;
  border-radius: 24px;
  border-style: none;
  box-sizing: border-box;
  color: $color-d;
  cursor: pointer;
  display: inline-flex;
  fill: currentcolor;
  font-family: "Baloo 2";
  font-size: 14px;
  font-weight: 600;
  height: 48px;
  justify-content: center;
  letter-spacing: 0.25px;
  line-height: normal;
  max-width: 100%;
  overflow: visible;
  padding: 2px 24px;
  position: relative;
  text-align: center;
  text-transform: none;
  transition: box-shadow 280ms cubic-bezier(0.4, 0, 0.2, 1),
    opacity 15ms linear 30ms, transform 270ms cubic-bezier(0, 0, 0.2, 1) 0ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: auto;
  will-change: transform, opacity;
  z-index: 0;
  box-shadow: 10px 10px $color-c;
}

button:hover {
  box-shadow: 20px 20px $color-c;
}
</style>
