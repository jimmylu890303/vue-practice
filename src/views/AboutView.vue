<template>
  <div class="about">
    <NavBar></NavBar>
    <h1>This is an about page</h1>
    <PostView :post="filterPosts"></PostView>
  </div>
</template>

<script>
import NavBar from "../components/NavBar";
import PostView from "../components/PostView.vue";
export default {
  components: {
    NavBar,
    PostView,
  },
  computed: {
    filterPosts() {
      return this.$store.getters.filterPosts[4];
    },
  },
};
</script>
