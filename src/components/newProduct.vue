<template>
  <div>
    <a style="font-size:3vw;">NewProduct</a>
    <div class="newProduct">
      <div v-for="Product in Products" :key="Product.id" class="newProductItem">
        <div class="newProductItemInfo">
          <a href='https://pito0713.github.io/earIngProudct'>{{Product.name}}</a>
          <a style="float:right"  @click="showUp(Product.id)">
            <i class="far fa-heart" :class="{fas : Product.add }" ></i>
          </a>
          <br />
          <div style="padding-top:1vw;">
            <a>NT: {{Product.price}}</a>
          </div>
        </div>
        <div>
          <a href='https://pito0713.github.io/earIngProudct'>
          <img :src="Product.img" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      Products: [],
      
    };
  },
  methods: {
    showUp(i) {
      this.Products[i].add = !this.Products[i].add;
      console.log(this.Products[i].add);
    }
  },
  mounted() {
    fetch("https://pito0713.github.io/Fetch/newProudcut.json")
      .then(res => {
        return res.json();
      })
      .then(Products => {
        this.Products = Products;
      });
  }
};
</script>
<style scoped lang="scss">
.newProduct {
  display: flex;
  position: relative;
  flex-wrap: wrap;
  padding-top: 2vw;
  margin-bottom: 8vw;
}
.newProductItem {
  display: flex;
  flex-direction: column;
  flex: 30%;
  padding: 0.25vw;
  margin: 0.5vw;
  transition: all 0.3s ease;
  img {
    max-width: 100%;
    max-height: 100%;
  }
}
.newProductItem:hover {
  transform: scale(1.05);
  box-shadow: var(--shadow);
}
.newProductItemInfo {
  text-align: start;
  padding: 0.5vw;
  a {
    font-size: 1.2vw;
    color: var(--product-color);
  }
}
@media screen and (max-width:769px){
    .newProductItem {
 
  flex: 45%;
    }
}
</style>