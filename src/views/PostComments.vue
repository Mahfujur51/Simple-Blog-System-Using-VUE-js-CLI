<template>
  <div class="card mt-3">
    <div class="card-header">POst Comment</div>
    <div class="row" v-for="comment in comments" :key="comment.id">
      <div class="col-md-2">
        <img src="@/assets/logo.png" class="card-image" alt />
      </div>
      <div class="col-md-10">
        <div class="card-body">
          <div class="card-title bg-dark text-light">{{comment.name}}</div>
          <div class="card-text">
            <p>{{comment.body}}</p>
            <small class="card-footer">{{comment.email}}</small>
          </div>
        </div>
      </div>
      <hr />
    </div>
  </div>
</template>



<script>
import axios from "axios";
export default {
  name: "PostComments",
  data() {
    return {
      id: this.$route.params.id,
      comments: []
    };
  },
  created() {
    axios
      .get(`https://jsonplaceholder.typicode.com/comments?postId=${this.id}`)
      .then(res => {
        this.comments = res.data;
      })
      .catch(e => {
        this.errors.push(e);
      });
  }
};
</script>
<style>
</style>    