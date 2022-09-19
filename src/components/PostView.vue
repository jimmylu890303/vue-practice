<template>
  <div>
    <div class="post-container">
      <button class="close-btn" @click="close()"></button>
      <h1>{{ post.title }}</h1>
      <h2>
        {{ post.body }}
      </h2>
      <img class="post-img" src="https://picsum.photos/600/300/?image=25" />
    </div>
  </div>
</template>

<script>
export default {
  name: "PostView",
  props: {
    post: Object,
  },
  methods: {
    close() {
      return this.$store.commit("setShow");
    },
  },
};
</script>

<style scoped>
div.post-container {
  position: relative;
  border: 2px solid;
  border-color: red;
  padding-top: 40px;
  padding-bottom: 20px;
  max-width: 800px;
  max-height: 1000px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 40px;
  margin-bottom: 20px;
  background-color: blanchedalmond;
}
h2 {
  word-wrap: break-word;
  word-break: break-all;
  border: 2px solid;
  border-color: rgb(98, 0, 255);
  margin-bottom: 30px;
  padding: 10px;
}
h1 {
  word-wrap: break-word;
  word-break: break-all;
  border: 2px solid;
  border-color: green;
  margin-bottom: 30px;
}
.post-img {
  border: 2px solid;
  border-color: yellow;
  max-width: 100%;
  max-height: 100%;
  margin-bottom: 0px;
}
.close-btn {
  margin-left: auto;
  position: absolute;
  top: 0;
  right: 0;
  background-image: url("../assets/close-button.png");
  width: 20px;
  height: 20px;
}
.close-btn:hover {
  opacity: 0.5;
}
</style>
