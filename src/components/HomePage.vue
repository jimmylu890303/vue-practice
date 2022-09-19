<template>
  <div class="homepage">
    <div class="posts">
      <PostCard
        v-if="showStatus"
        :cardlist="filterPosts"
        :postCount="postCount"
      ></PostCard>
      <PostView v-else :post="nowPost"></PostView>
    </div>
  </div>
</template>

<script>
import PostCard from "./PostCard";
import PostView from "./PostView.vue";
export default {
  name: "HomePage",
  components: {
    PostCard,
    PostView,
  },
  computed: {
    filterPosts() {
      return this.$store.getters.filterPosts;
    },
    postCount() {
      return this.filterPosts.length;
    },
    nowPost: {
      get() {
        return this.$store.state.nowPost;
      },
      set(val) {
        this.$store.commit("setNowPost", val);
      },
    },
    showStatus: {
      get() {
        return this.$store.state.show;
      },
    },
  },
  data() {
    return {
      show: Boolean,
    };
  },
};
</script>
