<template>
  <div class="main">
    <Navbar class="container"/>
    <homePageCarousel />
    <platform class="container"/>

  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import homePageCarousel from "@/components/homePageCarousel.vue";
import platform from "@/components/platform.vue";

export default {
  components: {
    Navbar,
    homePageCarousel,
    platform
  }
};
</script>
<style scoped lang="scss">
.main{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>