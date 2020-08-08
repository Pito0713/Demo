<template>
  <div class="container">
    <Navbar />
    <homePageCarousel />
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import homePageCarousel from "@/components/homePageCarousel.vue";

export default {
  components: {
    Navbar,
    homePageCarousel
  }
};
</script>
