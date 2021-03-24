<template lang="">
  <div class="container-sm">
    <h1>{{ thought.message }}</h1>
    <h3>
      Given hearts: <span class="fas fa-heart"></span> {{ thought.hearts }}
    </h3>
    <button class="heart-btn" @click="handleLikeThought">Add heart!</button>
  </div>
</template>
<script>
export default {
  name: "Thought",
  props: ["thought"],
  methods: {
    handleLikeThought() {
      this.$emit("thoughtLiked", this.thought._id);
    },
  },
};
</script>
<style scoped>
h1 {
  color: brown;
}
button {
  background-color: black;
  color: white;
  border-radius: 10px;
  padding: 10px 26px;
  font-family: "fira code";
}
</style>
