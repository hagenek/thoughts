<template lang="en">
  <div class="main-container">
  <v-container>
  <v-row no-gutters>
    <div v-for="thought in thoughts">
    <v-col md="6">
      <Thought @thoughtLiked="handleThoughtLiked" :thought=thought />
    </v-col>
    </div>
    </v-row>
    </v-container>
  </div>
</template>
<script>
import Thought from "./Thought";

export default {
  name: "Thoughts",
  components: {
    Thought,
  },
  data() {
    return {
      thoughts: [],
    };
  },
  methods: {
    handleThoughtLiked(id) {
      this.thoughts.find((thought) => thought._id !== id);
      console.log("A thought was liked" + id);
    },
  },
  created() {
    fetch(" https://happy-thoughts-technigo.herokuapp.com/thoughts")
      .then((res) => res.json())
      .then((res) => (this.thoughts = res));
  },
};
</script>
<style>
li {
  font-size: 20px;
}

.main-container {
  background: lightgray;
  display: flex;
  justify-content: center;
  flex-direction: row;
  align-items: center;
}
</style>
