<template>
  <div class="main">
    <Navbar />
    <homePageCarousel />
    <newArrivals class="container"/>
    <newProduct class="container"/>
    <platform class="container"/>
    <model class="container"/>
    <category class="container"/>
    <expansion class="container"/>
    <sciocal class="container"/>
    <discount class="container"/>
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import homePageCarousel from "@/components/homePageCarousel.vue";
import platform from "@/components/platform.vue";
import newProduct from "@/components/newProduct.vue";
import newArrivals from "@/components/newArrivals.vue";
import model from "@/components/model.vue";
import category from "@/components/category.vue";
import expansion from "@/components/expansion.vue";
import sciocal from "@/components/sciocal.vue";
import discount from "@/components/discount.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Navbar,
    homePageCarousel,
    platform,
    newArrivals,
    model,
    newProduct,
    category,
    expansion,
    sciocal,
    discount,
    Footer
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