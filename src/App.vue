<script>
import Block from "./components/Block.vue";
export default {
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      // console.log(this.delay);
    },
  },
};
</script>

<template>
  <h1>Reaction Timer</h1>
  <h2>from The Net Ninja's Tutorial</h2>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" />
</template>

<style>
@import "./assets/base.css";

#app {
  max-width: 1280px;
  margin: 60px auto;
  padding: 2rem;
  font-weight: normal;
  text-align: center;
}
</style>
