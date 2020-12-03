<template>
  <div class="block" v-if="showBlock">
    click me
  </div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
    }, this.delay);
  },
};
</script>

<style>
.block {
  width: 400px;
  padding: 100px 0;
  margin: 40px auto;
  text-align: center;
  color: #fff;
  background: #41b883;
  border-radius: 20px;
}
</style>
