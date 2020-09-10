<template>
  <div class="newArrivals">
    <a style="position: absolute; top:-10%; left:10%;">NeW Arrive</a>
    <div class="newArrivals-container">
      <div class="newArrivals-part" style="margin-right: 0rem; padding-right: 0rem; flex:40%;">
        <div class="newArrivals-product">
          <img src="../assets/newArrive1.jpg" alt srcset />
        </div>
        <div class="newArrivals-Info" >
          <p>8月新品上架</p>
          <p>Hot Sale</p>

        </div>
      </div>
      <div class="newArrivals-part" style="margin-left: 0rem; padding-left: 0rem; flex:60%;">
        <div class="newArrivals-product" >
         <img src="../assets/newArrive3.jpg" style="max-width: calc(50% - 0.6rem);" alt srcset />

          <img src="../assets/newArrive2.jpg" style="max-width: calc(50% - 0.6rem);" alt srcset />
        </div>
        <div class="newArrivals-product" >
          <img src="../assets/newArrive4.jpg"  alt srcset />
          
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>
<style scoped lang="scss">
.newArrivals {
  position: relative;
  a{
    font-size: 6vw;
  }
}
.newArrivals-container {
  border: 1px solid var(--border-color);
  display: flex;
  margin-bottom: 10vw;
  img {
    max-width: 100%;
  }

}
.newArrivals-part {
  flex: 50%;
  flex-direction: column;
  display: flex;
  padding: 1vw;
  margin: 0.5rem;
}
.newArrivals-product{
  display: flex;
}
.newArrivals-product img {
  max-width: calc(100% - 0.6rem);
  padding: 0.3rem;
}
.newArrivals-Info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  p{
    font-size: 3vw;
  }
  background-color: var(--background-color);
  margin: 0.3rem;
}
</style>