<template>
  <div class="container">
      <nuxt-link to="/" class="btn btn-danger my-5"> Go back</nuxt-link>
  </div>
</template>

<script>
// import axios from 'axios'
export default {
  name: 'PreviewMovie',
  async fetch () {
    // await this.getSingleMovie()
  },
  data () {
    return {
      movie: ''
    }
  }
//   methods: {
//     async getSingleMovie () {
//       const data = axios.get(
//         `https://api.themoviedb.org/3/movie/${this.$route.params.id}?api_key=574a726cd5f06cbe52c288a00c42de08&language=en-US&page=1`
//       )
//       const result = await data
//       this.movie = result.data
//       console.log(this.movie)
//     }
//   }
}
</script>

<style></style>
