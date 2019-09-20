<template>
  <div>
    <!-- PART 1: Pass in a "complete" prop here -->
    <Instructions complete='completed'/>
    <!-- PART 6: User input-->
    <form @submit.prevent="addShow">
      <label>Show Name</label>
      <input v-model="newShow" type="text">
      <button type="submit">Submit</button>
    </form>
    <!-- PART 4: Modify the Show component to accept all of these props -->
    <Show
      v-for="show in shows"
      :key="show.id"
      :id="show.id"
      :name="show.name"
      :episodes_seen="show.episodes_seen"
    />
  </div>
</template>

<script>
import Instructions from "./Instructions.vue";
import Show from "./Show.vue";

export default {
  components: {
    Instructions,
    Show
  },
  methods: {
    addShow() {
      let id = this.shows.length + 1;
      let name = this.newShow;
      let episodes_seen = 0;
      let show = {
        id: id,
        name: name,
        episodes_seen: episodes_seen
      }
      this.shows.push(show);
    }
  },
  data() {
    return {
      newShow: "",
      shows: [
        { id: 1, name: "Game of Thrones", episodes_seen: 0 },
        { id: 2, name: "Naruto", episodes_seen: 220 },
        { id: 3, name: "Black Mirror", episodes_seen: 3 }
      ]
    };
  }
};
</script>

<style>
</style>


