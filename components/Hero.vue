<template>
  <div class="hero">
      <div class="container d-flex">
          <div class="row m-auto">
              <div class="col ">
              <h6 class="text-danger">NOW STREAMING</h6>
              <h1 class="text-white">NOW STREAMING</h1>
              <a href="#movie-grid" class="btn btn-danger">VIEW MOVIES</a>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
*{
    /* margin: 0; */
    /* padding: 0; */
    box-sizing: border-box;
}
.hero{
    background-image: linear-gradient(rgba(10,10,10,0.8),rgba(10,10,10,0.8),rgba(10,10,10,0.8)), url("../assets/images/hero.jpg");
    background-size: cover;
    height: 100vh;
}
.col{
    margin: auto !important;
}
h1{
    font-size: 6vw;
}
.row{
    position: absolute;
    top: 30%;
}
</style>
