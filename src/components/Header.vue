<template>
  <div class="header container-fluid">
    <h1 class="headerText">
      <span>NASA:</span> Picture of the Day
      <div>Thursday, May 5, 2022</div>
    </h1>
    <img
      class="headerImage img-fluid img-responsive W-100"
      src="https://apod.nasa.gov/apod/image/2205/NGC3521LRGBHaAPOD-20.jpg"
    />
  </div>
</template>

<script>
export default {
  name: 'TopHeader',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
