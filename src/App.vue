<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
export default {
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      // console.log(this.delay);
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
  },
};
</script>

<template>
  <h1>Reaction Timer</h1>
  <h2>from The Net Ninja's Tutorial</h2>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
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

button {
  background-color: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 16px;
  cursor: pointer;
  margin: 1àpx;
}

button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
