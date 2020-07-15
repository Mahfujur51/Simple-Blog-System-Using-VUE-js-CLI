<template>
<div class="container">
  <div class="card">
  <div class="card-header">
       {{post.title}}
     
     
  </div>
  <div class="card-body">
    <div class="card-text">
      {{post.body}}
    </div>
  </div>
</div>
</div>


</template>



<script>
import axios from "axios";
export default {
  name: "PostDetails",
  data(){
    return {
      id: this.$route.params.id,
      post: []
    };
  },
  created(){
    axios.get(`https://jsonplaceholder.typicode.com/posts/${this.id}`)
    .then( res=>{
      this.post=res.data
    })
    .catch(e=>{
      this.errors.push(e);
    });
  }
};
</script>
<style>
</style>    