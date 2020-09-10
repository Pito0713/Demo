<template>
 <div class="category">
     <div class="categoryTile"><a >Wearing</a></div>
     
     <div class="categoryItem">
     <div v-for="img in imgDatas" :key="img.id" class="categoryImg">
     <img :src="require(`../assets/${img.url}.jpg`)" :alt='img.class'>
     <a>{{img.info}}</a>
     </div>
     </div>
 </div>
</template>

<script>
export default {
  data: function() {
    return {
      imgDatas:[
          {
              id : 1,
              url : 'categroy-season',
              class : 'seasonRing',
              info : 'Seasonal',
          },
          {
              id : 2,
              url : 'categroy-ring',
              class : 'earring',
              info : 'Earring'
          },
          {
              id : 3,
              url : 'categroy-necklace',
              class : 'necklace',
              info : 'Necklace'
          }
      ]

    };
  },
};
</script>

<style scoped lang="scss">
.category{
    position: relative;
    margin: 1vw;
}
.categoryItem{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    img{
        max-width: 100%;
    }
}
.categoryTile{
    width: calc(100% - 2vw);
    height: 10vw;
    position: absolute;
    top:-45%;
    left: 0%;
    z-index: 2;
    background-color: var(--background-color);
    font-size: 10vw;
    text-align: start;
    margin: 1vw 1vw 0 1vw ;
}
.categoryImg {
    padding:1.5vw 1vw 1vw 1vw;
    position: relative;
     a{
        position: absolute;
        bottom: 5%;
        left: 10%;
        font-size: 5vw;
        color: #ffffff;
    }
}


</style>
