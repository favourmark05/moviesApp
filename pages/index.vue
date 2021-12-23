<template>
  <div>
    <hero />
    <div class="container pt-5">
      <div class="form-group">
        <form action="">
          <input type="text" placeholder="Search for movies">
        </form>
      </div>
    </div>
    <div class="container d-flex" id="movie-grid">
      <div class="row justify-content-center">
        <div class="col-md-3 shadow m-3" v-for="(movie, index) in movies" :key="index">
          <div class="card mx-auto" style="width: 18rem;">
            <div class="img-sec">
              <img :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`" class="card-img-top border " alt="...">
            </div>
              <div class="review">
                <!-- <p> {{ movie.overview }} </p> -->
              </div>
            <div class="card-body">
              <p class="rating"> {{ movie.vote_average}} </p>
              <span class="card-title font-weight-bold"> {{ movie.title }} </span>
              <p><b>Released Date:</b> {{ movie.release_date }}</p>
            </div>
            <nuxt-link :to="{ name: 'movies-moviesid', params: { moviesid: movie.id } }" class="btn btn-danger">About</nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async fetch () {
    await this.getMovies()
  },
  data () {
    return {
      movies: [],
      spinner: false
    }
  },
  methods: {
    async getMovies () {
      // let load = loading
      const data = axios.get(
        'https://api.themoviedb.org/3/movie/now_playing?api_key=574a726cd5f06cbe52c288a00c42de08&language=en-US&page=1'
      )
      const result = await data
      result.data.results.forEach((movie) => {
        this.movies.push(movie)
        this.spinner = true
      })
      // console.log(this.movies)
    }
  }
}
</script>

<style scoped>
.rating{
  display: block;
  position: absolute !important;
  top: 0;
  left: 0;
  background-color: red;
  color: white;
  padding: 5px 10px;
  border-radius: .3em;
}
</style>
