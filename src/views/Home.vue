<template>
  <div class="main">
    <Navbar />
    <homePageCarousel />
    
    <newArrivals class="container"/>
    <newProduct class="container"/>
    <model class="container"/>
    <platform class="container"/>
    <category class="container"/>
    <discount class="container"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import homePageCarousel from "@/components/homePageCarousel.vue";
import platform from "@/components/platform.vue";
import discount from "@/components/discount.vue";
import newProduct from "@/components/newProduct.vue";
import newArrivals from "@/components/newArrivals.vue";
import model from "@/components/model.vue";
import category from "@/components/category.vue";


export default {
  components: {
    Navbar,
    homePageCarousel,
    platform,
    discount,
    newArrivals,
    model,
    newProduct,
    category
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