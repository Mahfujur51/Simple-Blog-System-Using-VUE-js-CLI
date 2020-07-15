<template>
  <div class="home">
    <AddPost />
    <PostList v-bind:posts="posts" />
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";
import AddPost from "@/views/AddPost.vue";
import PostList from "@/views/PostList.vue";

export default {
  name: "Home",
  components: {
    AddPost,
    PostList
  },
  data(){
    return {
     posts: [],
     errors: []
    };
  },
  created(){
    axios.get(`https://jsonplaceholder.typicode.com/posts?_limit=5`)
    .then( res=>{
      this.posts=res.data
    })
    .catch(e=>{
      this.errors.push(e);
    });
  }
};
</script>
