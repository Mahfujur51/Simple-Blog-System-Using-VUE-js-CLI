<template>
  <div class="container">
    <div
      class="card mt-3"
      v-for="post of posts"
      :key="post.id"
      @dblclick="$emit('delete-post',post.id)"
    >
      <div class="card-header text-left">
        <router-link :to="`/post-details/${post.id}`">{{post.title}}</router-link>
      </div>
      <div class="card-body">{{post.body}}</div>
    </div>
    <div class="card mt-3" v-if="errors && errors.length">
      >
      <div class="card-body">
        <p v-for="(error,index) of errors" :key="index">{{error.message}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PostList",
  props: ["posts"]
};
</script>
<style>
</style>