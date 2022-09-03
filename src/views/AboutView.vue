<script setup lang="ts">
import IconGitHub from "../components/icons/IconGitHub.vue";
import IconLinkedIn from "../components/icons/IconLinkedIn.vue";
import IconEnvelope from "../components/icons/IconEnvelope.vue";
</script>

<template>
  <main>
    <div class="container">
      <h1>About Rubber Duck</h1>
      <p>
        This app is here to help you find and solve your problems. Based on the
        <a href="https://en.wikipedia.org/wiki/Rubber_duck_debugging"
          >rubber duck debugging method</a
        >, it is mostly focused on helping software engineers to get rid of the
        bugs in their code. However, everyone is welcome to consult the duck
        with any sort of problem.
      </p>
      <br />
      <p>
        Begin by explaining your problem to the duck. Remember to be as specific
        as possible; the duck does not know anything about your problem, you
        must introduce it to the topic.
      </p>
      <br />
      <p>
        We often think we understand a problem and fail to realise that we have
        missed possible solutions. By having to explain the problem to someone
        who knows nothing about it, one is forced to confront all parts and
        perspectives of it, which is often enough to find the solution.
      </p>
      <br />
      <p>
        See the rubber duck debugging method steps
        <a
          href="http://lists.ethernal.org/oldarchives/cantlug-0211/msg00174.html"
          >here</a
        >.
      </p>
      <h1>About me</h1>
      <p>
        Hey, I'm Veronika, a full-stack developer based in Bratislava, Slovakia.
      </p>
      <br />
      <p>Feel free to reach me here:</p>
      <div class="contact-line">
        <IconGitHub />
        <a href="https://github.com/vrusi">vrusi</a>
      </div>
      <div class="contact-line">
        <IconLinkedIn />
        <a href="https://www.linkedin.com/in/veronika-rusinkova-6b012718a/"
          >Veronika Rusinkova</a
        >
      </div>
      <div class="contact-line">
        <IconEnvelope />
        <a href="mailto: me@vrusinkova.com">me@vrusinkova.com</a>
      </div>
    </div>
  </main>
</template>

<style lang="scss">
@import "../assets/colours.scss";

.contact-line {
  display: flex;
  align-items: center;
  color: $colour-primary;
  margin-bottom: 0.5rem;
}

.contact-line a {
  margin-left: 1rem;
  font-size: 1.5rem;
  font-weight: 500;
}

@media (prefers-color-scheme: dark) {
  .contact-line {
    color: $colour-primary-dark;
  }
}
</style>
