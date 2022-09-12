<template>
  <div class="homepage">
    <div class="posts">
      <PostCard :cardlist="filterPosts" :postCount="postCount"></PostCard>
    </div>
  </div>
</template>

<script>
import PostCard from "./PostCard";
export default {
  name: "HomePage",
  components: {
    PostCard,
  },
  computed: {
    filterPosts() {
      return this.$store.getters.filterPosts;
    },
    postCount() {
      return this.filterPosts.length;
    },
  },
};
</script>
