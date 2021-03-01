<template>
  <div class="category" id="category">
    <div class="categoryTile" >
      <a>Product Category</a>
    </div>

    <div class="categoryItem">
      <div v-for="img in imgDatas" :key="img.id" class="categoryImg">
        <img :src="require(`../assets/${img.url}.jpg`)" :alt="img.class" />
        <a>{{img.info}}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      imgDatas: [
        {
          id: 1,
          url: "categroy-season",
          class: "seasonRing",
          info: "Seasonal"
        },
        {
          id: 2,
          url: "categroy-ring",
          class: "earring",
          info: "Earring"
        },
        {
          id: 3,
          url: "categroy-necklace",
          class: "necklace",
          info: "Necklace"
        }
      ]
    };
  }
};
</script>

<style scoped lang="scss">
@import url("https://fonts.googleapis.com/css2?family=El+Messiri:wght@600&display=swap");
.category {
  position: relative;
  margin: 1vw 1vw 0 1vw;
  font-family: "El Messiri", sans-serif;
}
.categoryItem {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  img {
    max-width: 100%;
  }
}
.categoryTile {
  width: calc(100% - 2vw);
  height: 8vw;
  position: absolute;
  
  top: -45%;
  left: 0%;
  z-index: 2;
  background-color: var(--background-color);
  font-size: 5vw;
  text-align: start;
  margin: 1vw 1vw 0 1vw;
}
.categoryImg {
  padding: 1.5vw 1vw 0vw 1vw;
  position: relative;
  a {
    position: absolute;
    bottom: 2%;
    left: 10%;
    font-size: 4vw;
    color: #ffffff;
    z-index: 1;
  }

}
.categoryImg::after {
    content: " ";
    position: absolute;
    display: block;
    width: 70%;
    height: 10%;
    bottom: 7%;
    z-index: 0;
    background-color: var(--title-color);
  }
</style>
