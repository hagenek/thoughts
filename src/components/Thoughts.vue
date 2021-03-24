<template lang="en">
  <div class="main-container">
    <div v-for="thought in thoughts">
      <Thought @thoughtLiked="handleThoughtLiked" :thought=thought />
    </div>
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
<style scoped>
li {
  font-size: 20px;
}

.main-container {
  max-width: 800px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
</style>
