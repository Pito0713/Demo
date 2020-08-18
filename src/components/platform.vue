<template>
  <div class="plat">
    <div class="platImg" style="flex:30%">
      <img style="flex:50%" src="../assets/platButterfly1.jpg" alt srcset />
      <a style="flex:50%">ButterFly</a>
    </div>
    <div class="platImgMiddle" style="flex:40%">
        <img src="../assets/platModel2.jpg" alt="" srcset="">
    </div>
    <div class="platImg" style="flex:30%">
      <a style="flex:50%">Retro Jewelry</a>
      <img style="flex:50%" src="../assets/plat2.jpg" alt srcset />
    </div>
  </div>
</template>

<script>
export default {};
</script>
<style scoped lang="scss">
.plat {
  display: flex;
  position: relative;
  padding-top: 4rem;
  img {
    max-width: 100%;
  }
}
.platImg {
  padding:0  0.5rem;
  display: flex;
  position: relative;
  flex-direction: column;
  a {
    font-size: 2.5rem;
    font-family: var(--font-Caveat);
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>