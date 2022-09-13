<template>
  <!----
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
-->
  <div>
    <div class="conatainer">
      <h2></h2>
      <div>
        <input class="search-input" placeholder="文章搜尋" />
        <button class="search-btn">search</button>
      </div>
      <span>{{ postCount }}則貼文</span>
      <div class="post-cards">
        <div class="post" v-for="post in cardlist" :key="post.id">
          <img class="post-img" src="https://picsum.photos/600/300/?image=25" />
          <h1 class="post-title">{{ post.title }}</h1>
          <p class="post-content">
            {{ post.body }}
          </p>
          <button class="post-btn" href="#" variant="primary">see more</button>
        </div>
      </div>
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

<style scoped>
.search-input {
  margin-top: 30px;
  margin-bottom: 30px;
  height: 50px;
  width: 70%;
  padding: 15px;
}
.search-btn {
  display: block;
  margin: auto;
  width: 7%;
  padding: 10px;
  margin-bottom: 30px;
  text-align: center;
  border-style: solid;
  border-width: medium;
  border-color: lightblue;
  border-radius: 10px;
  background-color: aquamarine;
  font-size: 30px;
  font-weight: bold;
  color: green;
}
div.post {
  border-style: solid;
  border-width: medium;
  border-color: lightblue;
  border-left-color: lightgreen;
  border-left-width: 20px;
  border-radius: 10px;
  margin: 20px;
  padding: 10px;
  width: 20%;
  display: inline-block;
  height: 600px;
}
.post-img {
  width: 100%;
}
.post-title {
  text-align: center;
  color: green;
  text-shadow: 2px 2px 5px greenyellow;
  font-weight: bold;
  font-size: 45px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.post-content {
  height: 30%;
  font-size: 20px;
  overflow: auto;
}
.post-btn {
  background-color: blue;
  border-radius: 10px;
  width: 30%;
  color: white;
  padding: 10px 5px 10px 5px;
  margin-bottom: 10px;
  font-size: 25px;
}
.post-btn:hover {
  opacity: 0.7;
  width: 40%;
}
</style>
