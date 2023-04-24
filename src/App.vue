<template>
  <main>
    <TipCalculator />
    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
      Coded by <a href="#">Your Name Here</a>.
    </div>
  </main>
</template>

<script>
import TipCalculator from './components/TipCalculator.vue'

export default {
  name: 'App',
  components: {
    TipCalculator
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono&display=swap');

.v-application{
  font-family: "Space Mono";
}
html {
  height: 100%;
  font-family: "Space Mono";
}

body {
  height: 100%;
  margin: 0;
  background-color: hsl(185, 41%, 84%);
  
}

#app {
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  width: 100%;
}

.attribution {
  font-size: 11px;
  text-align: center;
  margin-top: 1rem;
}

.attribution a {
  color: hsl(228, 45%, 44%);
}</style>
