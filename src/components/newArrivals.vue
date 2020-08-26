<template>
  <div class="newArrivals">
    <a style="position: absolute; top:-10%; left:10%;">NeW Arrive</a>
    <div class="newArrivals-container">
      <div class="newArrivals-part" style="margin-right: 0rem; padding-right: 0rem;">
        <div class="newArrivals-product" style="flex:40%;">
          <img src="../assets/newArrive-3.jpg" alt srcset />
          <img src="../assets/newArrive-2.jpg" alt srcset />
        </div>
        <div class="newArrivals-Info" style="flex:60%;">
          <img src="../assets/newArrive-4.jpg" alt srcset />
        </div>
      </div>
      <div class="newArrivals-part" style="margin-left: 0rem; padding-left: 0rem;">
        <div class="newArrivals-product" style="flex:70%;">
          <img src="../assets/newArrive-7.jpg" style="max-width:calc(60% - 0.6rem)" alt srcset />
          <img src="../assets/newArrive-6.jpg" style="max-width:calc(40% - 0.6rem)" alt srcset />
        </div>
        <div class="newArrivals-Info" style="flex:30%;">
          <img src="../assets/newArrive-5.jpg" alt srcset />
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
  margin-bottom: 20vw;
  img {
    max-width: 100%;
  }
  .newArrivals-product {
    display: flex;
  }
}
.newArrivals-part {
  flex: 50%;
  flex-direction: column;
  display: flex;
  padding: 1vw;
  margin: 0.5rem;
}
.newArrivals-product img {
  max-width: calc(50% - 0.6rem);
  padding: 0.3rem;
}
.newArrivals-Info img {
  max-width: calc(100% - 0.6rem);
  padding: 0.3rem;
}
</style>