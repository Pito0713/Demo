<template>
  <div class="newArrivals">
    <a style="position: absolute; top:-8vw; left:5%;">
      NeW Arrive
      <i>d(`･∀･)b</i>
    </a>

    <div class="newArrivals-container">
      <div class="newArrivals-part" style="margin-right: 0rem; padding-right: 0rem; flex:45%;">
        <img src="../assets/newArrive1.jpg" alt srcset />
        <div class="newArrivals-Info">
          <p>8月新品上架</p>
          <a>New items</a>
        </div>
      </div>
      <div class="newArrivals-part" style="margin-left: 0rem; padding-left: 0rem; flex:60%;">
        <div class="newArrivals-Img">
          <img src="../assets/newArrive3.jpg" style="max-width: calc(50% - 0.6vw); " alt srcset />
          <img src="../assets/newArrive2.jpg" style="max-width: calc(50% - 0.6vw); " alt srcset />
        </div>

        <img
          src="../assets/newArrive4.jpg"
          style=" max-width: calc(100% - 0.6vw);"
          alt
          srcset
          max-height="100%"
        />
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
  padding-bottom: 8vw;
  border-bottom: 1px solid var(--border-color);
  a {
    font-size: 8vw;
    font-family: var(--font-Caveat);
    i {
      font-size: 2vw;
      font-family: var(--font-Pragati);
      padding-left: 3vw;
    }
  }
}
.newArrivals-Img {
  display: flex;
  justify-content: center;
  align-items: center;
}
.newArrivals-container {
  border: 1px solid var(--border-color);
  display: flex;
}
.newArrivals-part {
  flex-direction: column;
  display: flex;
  padding: 1vw;
  margin: 0.5rem;
}
.newArrivals-part img {
  max-width: calc(100% - 0.6vw);
  padding: 0.3vw;
}
.newArrivals-Info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  p,
  a {
    font-size: 3vw;
  }
  background-color: var(--background-color);
  margin: 0.3vw;
}
</style>