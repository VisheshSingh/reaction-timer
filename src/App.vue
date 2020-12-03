<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Result v-if="showScore" :score="score" />
</template>

<script>
import Block from './components/Block';
import Result from './components/Result';

export default {
  name: 'App',
  components: {
    Block,
    Result,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showScore: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showScore = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showScore = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  background: #41b883;
  padding: 10px 20px;
  border: none;
  border-radius: 10px;
  color: #fff;
}
button:disabled {
  background: #6d6e6e;
  cursor: not-allowed;
}
</style>
