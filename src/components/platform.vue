<template>
  <div class="plat">
      <div class="platImg" style="flex:30%">
          <img style="flex:50%" src="../assets/plat1.jpg" alt="" srcset="">
          <a style="flex:50%">123</a>
      </div>
      <div class="platImg" style="flex:40%">
          <img src="../assets/platModel.jpg" alt="" srcset="">
      </div>
      <div class="platImg" style="flex:30%">
          <a style="flex:50%">123</a>
          <img style="flex:50%" src="../assets/plat2.jpg" alt="" srcset="">
      </div>
  </div>
</template>

<script>
export default {

};
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
    padding: 0.5rem;
    display: flex;
    position: relative;
    flex-direction: column;
}
</style>