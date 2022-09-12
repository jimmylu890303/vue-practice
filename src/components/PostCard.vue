<template>
  <div>
    <div>
      <b-container>
        <b-col class="m-5 text-center">
          <h2></h2>
        </b-col>
        <b-row align-h="center" class="m-5">
          <b-form-input placeholder="搜尋貼文" v-model="keyword"></b-form-input>
        </b-row>
        <br />
        <span>{{ postCount }}則貼文</span>
        <b-row rows="8" align-h="center" class="m-3">
          <div v-for="post in cardlist" :key="post.id">
            <b-card
              img-src="https://picsum.photos/600/300/?image=25"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-title>{{ post.title }}</b-card-title>
              <b-card-text>
                {{ post.content }}
              </b-card-text>
              <b-button href="#" variant="primary">Go somewhere</b-button>
            </b-card>
          </div>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {
  name: "PostCard",
  data() {
    return {};
  },
  computed: {
    keyword: {
      get() {
        return this.$store.state.keyword;
      },
      set(val) {
        this.$store.commit("setKeyword", val);
      },
    },
  },
  props: {
    cardlist: { type: Array },
    postCount: Number,
  },
};
</script>
