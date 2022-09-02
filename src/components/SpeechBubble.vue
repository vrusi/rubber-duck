<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";

const messages = [
  "What's your problem?",
  "What is it supposed to be doing?",
  "What did you do so far?",
  "What have you tried doing?",
  "How did you implement it?",
  "Can you explain step by step?",
  "I'm 5 years old. I've no idea what that means.",
  "I really don't get it. Can you be more specific about that?",
  "What were you expecting would happen?",
  "How is that not what you expected to happen?",
  "What is its responsibility?",
  "Does it depend on anything?",
  "Are you using a proper debugging tool or just printing 'here'?",
];

function getMessage() {
  return messages[Math.floor(Math.random() * messages.length)];
}

const currentMessage = ref(getMessage());

let intervalId = 0;
onMounted(() => {
  intervalId = setInterval(() => {
    currentMessage.value = getMessage();
  }, 30000);
});

onUnmounted(() => clearInterval(intervalId));
</script>

<template>
  <div class="speech-bubble">{{ currentMessage }}</div>
</template>

<style lang="scss" scoped>
@import "../assets/colours.scss";

.speech-bubble {
  transform: translatey(0px);
  animation: float 5s ease-in-out infinite;
  text-align: center;
  text-transform: uppercase;
  font-weight: bold;
  letter-spacing: 3px;
  font-size: 15px;
  color: $color-d;
  background-color: $color-a;
  padding: 50px;
  border-radius: 11px;
  position: relative;
  box-shadow: 20px 20px $color-c;
  font-family: "Baloo 2", cursive;
  // border: 1px solid $color-green;
}

.speech-bubble:after {
  transform: translatey(0px);
  animation: float2 5s ease-in-out infinite;
  content: ".";
  font-weight: bold;
  // -webkit-text-stroke: 0.5px $color-green;
  -webkit-text-fill-color: $color-a;
  // border: 1px solid $color-green;
  text-shadow: 22px 22px $color-c;
  text-align: right;
  font-size: 55px;
  width: 55px;
  height: 11px;
  line-height: 30px;
  border-radius: 11px;
  background-color: $color-a;
  position: absolute;
  display: block;
  bottom: -30px;
  left: 20px;
  box-shadow: 22px 22px $color-c;
  z-index: -2;
}

@keyframes float {
  0% {
    transform: translatey(0px);
  }

  50% {
    transform: translatey(-20px);
  }

  100% {
    transform: translatey(0px);
  }
}

@keyframes float2 {
  0% {
    line-height: 30px;
    transform: translatey(0px);
  }

  55% {
    transform: translatey(-20px);
  }

  60% {
    line-height: 10px;
  }

  100% {
    line-height: 30px;
    transform: translatey(0px);
  }
}
</style>
