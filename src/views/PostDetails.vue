<template>
  <div class="container">
    <div class="card">
      <div class="footer bg-info">
        <router-link to="/" class="btn btn-warning pull-right">Go Back to Main Pages</router-link>
      </div>
      <div class="card-header">{{post.title}}</div>
      <div class="card-body">
        <div class="card-text">{{post.body}}</div>
      </div>
    </div>
    <PostComments />
  </div>
</template>



<script>
import axios from "axios";
import PostComments from "@/views/PostComments.vue";
export default {
  name: "PostDetails",
  components: {
    PostComments
  },
  data() {
    return {
      id: this.$route.params.id,
      post: []
    };
  },
  created() {
    axios
      .get(`https://jsonplaceholder.typicode.com/posts/${this.id}`)
      .then(res => {
        this.post = res.data;
      })
      .catch(e => {
        this.errors.push(e);
      });
  }
};
</script>
<style>
</style>    