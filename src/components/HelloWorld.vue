<template lang="html">
  <div>
  <Navbar></Navbar>
  <!-- <Carousel></Carousel> -->
  <ParallaxNav></ParallaxNav>
  <Aboutus></Aboutus>
  <ParallaxAboutus></ParallaxAboutus>
  <Gmaps></Gmaps>
  </div>
</template>

<script>
import Navbar from './nav-bar.vue'
import Aboutus from './about-us.vue'
import Carousel from './carousel.vue'
import ParallaxNav from './parallax-under-Nav.vue'
import ParallaxAboutus from './parallax-aboutus.vue'
import Gmaps from './gmaps.vue'
export default {
  components: {
    Navbar,
    Aboutus,
    Carousel,
    ParallaxNav,
    ParallaxAboutus,
    Gmaps
  }
}
</script>

<style lang="css">

</style>
