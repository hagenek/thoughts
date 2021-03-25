<template>
  <v-app>
    <v-main>
      <Thoughts />
    </v-main>
  </v-app>
</template>

<script>
import Thoughts from "./components/Thoughts";

export default {
  name: "App",

  components: {
    Thoughts,
  },

  data: () => ({
    //
  }),
};
</script>

<style scoped>
body {
  background-color: grey;
}
</style>
