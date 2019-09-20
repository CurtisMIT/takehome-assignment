<template>
  <div>
    <p>I'm a Counter!</p>
    <h1>{{ count }}</h1>
    <button v-on:click="count += 1">+</button>
    <button v-on:click="count -= 1">-</button>
  </div>
  <!-- <p>I'm a Counter!</p> -->
</template>

<script>
export default {
  props: {
    episodes_seen: Number
  },
  data() {
    return {
      count: this.episodes_seen ? this.episodes_seen : 0
    };
  }
};
</script>

<style>
</style>

