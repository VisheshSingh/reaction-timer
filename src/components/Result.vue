<template>
  <p>Reaction time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = 'Ninja fingers 🐱‍👤';
    } else if (this.score < 400) {
      this.rank = 'Rapid reflexes 🏇';
    } else {
      this.rank = 'Snail pace 🐌';
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  font-weight: bold;
  color: #41b883;
}
</style>
