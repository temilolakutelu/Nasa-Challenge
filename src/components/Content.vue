/* eslint-disable vue/require-v-for-key */
<template>
  <div class="main mb-4">
    <div class="row">
      <div v-for="(row,ix) of movies_data" v-bind:key="ix" class="col-xl-3 col-lg-4 col-sm-6 mb-3">
        <div class="box">
          <a :href="'https://nasa-movies.netlify.app/movies/'+ row.id">
            <div class="img-container" :style="backgroundImageInlineStyle(row)"></div>
            <h1 class="title">{{row.original_title}}</h1>
            <h4 class="description">Description:</h4>
            <p class="overview">{{row.overview}}</p>
            <p class="label">
              Popularity:
              <em>{{row.popularity}}</em>
            </p>
            <p class="label">
              Release Date:
              <em>{{row.release_date}}</em>
            </p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import axios from 'axios';
export default {
  name: 'MainContent',
  data () {
    return {
      movies_data: []
    }
  },
  mounted () {
    this.getMovies()
  },
  methods: {
    getMovies () {
      let vm = this;
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=48b43c71c226d58239efb833d05ab17c&language=en-US&query=NASA&include_adult=false&1', {
      })
        .then(function (response) {
          console.log(response.data.results);
          vm.movies_data = response.data.results
        })
    },
    backgroundImageInlineStyle (row) {
      console.log(row)
      let image = row.poster_path !== null ? 'https://image.tmdb.org/t/p/original' + row.poster_path : 'https://nasa-movies.netlify.app/image/gallery.png'
      return 'background-image:url(' + image + ')';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only --> 
<style scoped>
</style>
