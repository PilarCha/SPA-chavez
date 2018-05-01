<template lang="html">
  <div>
  <Navbar></Navbar>
  <!-- <Carousel></Carousel> -->
  <Aboutus></Aboutus>
  </div>
</template>

<script>
import Navbar from './nav-bar.vue'
import Aboutus from './about-us.vue'
import Carousel from './carousel.vue'
export default {
  components: {
    Navbar,
    Aboutus,
    Carousel
  }
}
</script>

<style lang="css">

</style>
