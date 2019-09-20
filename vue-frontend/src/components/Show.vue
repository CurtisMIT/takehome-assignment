<template>
  <!-- PART 4: Add your code here -->
  <div>
    <h1>Show: {{ name }}</h1>
    <Counter v-bind:episodes_seen="this.episodes_seen"/>
  </div>
</template>

<script>
// PART 4: Add your code here
import Counter from "./Counter"

export default {
  components: {
    Counter
  },
  props: {
    id: Number,
    name: String,
    episodes_seen: Number
  }
};
</script>

<style>
</style>
