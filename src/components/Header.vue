<template>
<div class="wapper  bg-light">
<div class="container">
  <nav id="nav" class="navbar navbar-expand-lg navbar-light bg-light">
  <router-link class="navbar-brand" to="/">{{siteTitle}}</router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
        <router-link class="nav-link" to="/">Home <span class="sr-only">(current)</span></router-link>
      </li>
      <li class="nav-item">
        <router-link to="/about" class="nav-link" >About</router-link>

      </li>
     </ul>
  
  </div>
</nav>
</div>
</div>




  <!-- <div class="hello">
    <div id="nav">
     |
      
    </div>
  </div> -->
</template>

<script>
export default {
  name: "Header",
  data(){
    return{
      siteTitle: "Vue Basaic App"
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
