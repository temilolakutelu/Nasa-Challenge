<template>
  <div class="main">
    <div class="row container-fluid">
      <div class="box col-xl-2 col-lg-3 col-md-4 col-sm-6 m-2">
        <a href="/movies/706614">
          <img src />
          <h1 class="css-1srwy3f">NASA &amp; SpaceX: Journey to the Future</h1>
          <h4 class="css-fkz7sy">Description:</h4>
          <p
            class="css-tisqv0"
          >A film crew was granted unprecedented access to NASA and to SpaceX headquarters, giving viewers a rare glimpse inside Launch Control and firsthand accounts from SpaceX founder and chief engineer Elon Musk, Bridentstine and the astronauts flying the mission: Bob Behnken and Doug Hurley.</p>
          <p class="css-1q2plns">
            Popularity:
            <em>4.015</em>
          </p>
          <p class="css-1q2plns">
            Release Date:
            <em>2020-05-25</em>
          </p>
        </a>
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
      movie_data: []
    }
  },
  mounted () {
    this.getMovies()
  },
  methods: {
    getMovies () {
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=48b43c71c226d58239efb833d05ab17c&language=en-US&query=NASA&include_adult=false&1', {
      })
        .then(function (response) {
          console.log(response);
        })
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only --> 
<style scoped>
</style>
