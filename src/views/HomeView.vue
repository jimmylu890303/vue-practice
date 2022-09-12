<template>
  <div class="home">
    <NavBar></NavBar>
    <HomePage></HomePage>
  </div>
</template>

<script>
// @ is an alias to /src
import HomePage from "../components/HomePage";
import NavBar from "../components/NavBar";

export default {
  name: "HomeView",
  components: {
    HomePage,
    NavBar,
  },
  data() {
    return {};
  },
};
</script>
