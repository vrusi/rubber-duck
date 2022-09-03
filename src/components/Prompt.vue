<script setup lang="ts">
const placeholders = [
  "I'm implementing user registration and...",
  "My button component doesn't redirect. The way I wrote it is...",
  "I am working on a component which... ",
];

function getPlaceholder() {
  return placeholders[Math.floor(Math.random() * placeholders.length)];
}
</script>

<template>
  <div class="paper">
    <div class="lines">
      <div class="line" v-for="line in [...Array(10).keys()]"></div>
    </div>

    <textarea
      :placeholder="getPlaceholder()"
      rows="9"
      cols="50"
      autofocus
    ></textarea>
  </div>
</template>

<style lang="scss">
@import "../assets/colours.scss";

.lines {
  width: 60vw;
  height: 100%;
  grid-column: 1;
  grid-row: 1;
}

.line {
  width: 100%;
  height: 2rem;
  border-bottom: 1px rgba(0, 100, 255, 0.3) solid;
}

.paper {
  display: grid;
  width: 60vw;
  border-radius: 11px;
  background-color: #f2f2f2;
  margin: 2rem auto;
  box-shadow: 22px 22px $colour-background-dark;
}

.paper > textarea {
  word-wrap: break-word;
  resize: none;
  width: 54vw;
  height: 100%;
  background-color: transparent;
  margin: 0 0 0 4rem;
  border: none;
  border-left: 2px rgba(255, 0, 0, 0.3) solid;
  padding: 2rem 3rem 2rem 2rem;
  grid-column: 1;
  grid-row: 1;
  font-size: 1.5rem;
  line-height: 2rem;
  color: $colour-primary;
}

.paper > textarea::placeholder {
  color: rgba(144, 99, 97, 0.5);
}
.paper > textarea:focus {
  outline: none;
}

@media screen and (max-width: 380px) {
  .paper {
    margin: 1rem auto;
  }

  .paper > textarea {
    margin: 0 0 0 1rem;
    line-height: 1.5rem;
    font-size: 1rem;
    padding: 1.5rem 1rem;
  }

  .line {
    height: 1.5rem;
  }
}

@media screen and (min-width: 2560px) {
  .paper,
  .lines {
    max-width: 40vw;
  }

  .paper > textarea {
    max-width: 34vw;
  }
}
</style>
