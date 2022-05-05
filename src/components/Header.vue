<template>
  <div class="header container-fluid">
    <h1 class="headerText">
      <span>NASA:</span> Picture of the Day
      <div>{{formatDate(nasa_data.date)}}</div>
    </h1>
    <img
      :title="nasa_data.title"
      class="headerImage img-fluid img-responsive W-100"
      :src="nasa_data.hdurl"
    />
  </div>
</template>


<script>
import axios from 'axios';
export default {
  name: 'TopHeader',
  data () {
    return {
      nasa_data: {}
    }
  },
  mounted () {
    this.getNasaData();
  },
  methods: {
    //api to fetch header data
    getNasaData () {
      let vm = this;
      axios.get('https://api.nasa.gov/planetary/apod?api_key=SPkLKA7bCBamNIY9kJ4ceIeWB67uFjxP5lXkQeNR', {
      })
        .then(function (response) {
          console.log(response.data);
          vm.nasa_data = response.data
        })
    },
    formatDate (date) {
      if (date !== null) {
        let d = new Date(date)
        return d.toDateString().replace(' ', ', ')
      }
      else {
        return null
      }
    },

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
