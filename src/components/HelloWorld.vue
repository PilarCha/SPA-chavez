<template lang="html">
  <div>
  <Navbar></Navbar>
  <!-- <Carousel></Carousel> -->
  <ParallaxNav></ParallaxNav>
  <Aboutus></Aboutus>
  </div>
</template>

<script>
import Navbar from './nav-bar.vue'
import Aboutus from './about-us.vue'
import Carousel from './carousel.vue'
import ParallaxNav from './parallax-under-Nav.vue'
export default {
  components: {
    Navbar,
    Aboutus,
    Carousel,
    ParallaxNav
  }
}
</script>

<style lang="css">

</style>
