<template>
  <div class="newProduct">
    <div v-for="Product in Products" :key="Product.id" class="newProductItem">
      <div class="newProductItemInfo">
        <p>{{Product.id}}</p>
      </div>
      <div style="flex:80%">
        <img :src="Product.img" />
      </div>
    </div>  
  </div>
</template>

<script>

export default {
    data: function(){
        return{
            Products: [],
        }
      
    },
    mounted() {
    fetch('https://pito0713.github.io/Fetch/newProudcut.json')
     .then((res) => {
        return res.json()})
     .then((Products) => {
        this.Products = Products});
    },
};

</script>
<style scoped lang="scss">
.newProduct {
  display: flex;
  position: relative;
  flex-wrap: wrap;
  margin-bottom: 10vw;
}
.newProductItem {
  display: flex;
  flex-direction: column;
  flex: 30%;
  padding: 1vw;
  img {
    max-width: 100%;
    max-height: 100%;
  }
}
.newProductItemInfo{
    flex: 10vw;
    background-color: var(--background-color)
}
</style>