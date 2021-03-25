<template lang="">
  <v-container class="container">
    <v-card elevation="2">
      <v-card-title>{{ thought.message }}</v-card-title>
      <v-card-text>
        Given hearts: <span class="fas fa-heart"></span> {{ thought.hearts }}
      </v-card-text>
      <v-card-actions>
        <v-btn @click="handleLikeThought"><i class="fas fa-heart lg"/></v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
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

.container {
  width: 300px;
}
</style>
