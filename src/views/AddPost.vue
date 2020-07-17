<template>
  <div class="container">
    <div class="card mt-3">
      <div class="card-hader">
        <div class="text-center">
          <div class="center">
            <button class="btn btn-success btn-lg" @click="formShow">Create New post</button>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12">
        <div class="card bg-dark">
          <div class="card-text" v-if="formdiv">
            <form @submit.prevent="addPost">
              <div class="form-gorup">
                <label class="text-light pull-left">Post Title</label>
                <input
                  type="text"
                  name="title"
                  v-model="title"
                  class="form-control"
                  placeholder="Enter Post TItle"
                />
              </div>
              <div class="form-gorup">
                <label class="text-light pull-left">Post Description</label>
                <textarea
                  name="body"
                  v-model="body"
                  class="form-control"
                  id
                  cols="30"
                  rows="10"
                  placeholder="ENter post details"
                ></textarea>
              </div>
              <div class="form-gorup">
                <div class="text-center">
                  <button class="btn btn-block btn-success">Submit Post</button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>



<script>
export default {
  name: "AddPost",
  data() {
    return {
      formdiv: false,
      title: "",
      body: ""
    };
  },
  methods: {
    formShow() {
      this.formdiv = true;
    },
    addPost() {
      const newPost = {
        title: this.title,
        body: this.body
      };
      this.$emit("add-post", newPost);
      (this.title = ""), (this.body = "");
    }
  }
};
</script>
<style>
</style>    