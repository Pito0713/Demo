<template>
  <div class="plat">
    <div class="platImg" style="flex:30%; align-items: flex-start">
      <div style="flex:50%" class="platImgLeft">
        <img src="../assets/platButterfly.jpg" alt srcset />
        <div class="platImgText">
          <div class="line"></div>
          <a href>Be Fly</a>
          <div class="line"></div>
        </div>
      </div>

      <a style="flex:50%">ButterFly</a>
    </div>
    <div class="platImgMiddle" style="flex:40%">
      <img src="../assets/platModel.jpg" alt srcset />
    </div>
    <div class="platImg" style="flex:30%">
      <a style="flex:50%">Retro Jewelry</a>
      <!---<a class="platImgRight" href></a>-->
      <div style="flex:50%" class="platImgRight">
        <img src="../assets/platjewelry.jpg" alt srcset />
        <div class="platImgText">
          <div class="line" style="width: 20%;"></div>
          <a href>Be Elegant.</a>
          <div class="line" style="width: 20%;"></div>
        </div>
      </div>
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
  margin-bottom: 10vw;
  img {
    max-width: 100%;
    max-height: 100%;
  }
}
.platImg {
  padding: 0 0.5rem;
  display: flex;
  position: relative;
  flex-direction: column;
  a {
    font-size: 5vw;
    font-family: var(--font-Caveat);
    display: flex;
    align-items: center;
    justify-content: center;
    
  }
  img:hover {
    filter: blur(2px);
    opacity: 1;
    transition: 0.3s ease-in-out;
  }
}
.plat::before{
  content: "";
  display: block;
  position: absolute;
  left: 4vw;
  top:4vw;
  border: 1px solid var(--border-color);
  width: calc(100% - 8vw);
  height: calc(100% - 8vw);
}
.platImgLeft,
.platImgRight {
  position: relative;
  transition: 0.3s ease-in-out;
}
.platImgRight{
  display: flex;
  align-items: flex-end;
}
.line {
  display: block;
  position: relative;
  margin: 0.3rem;
  width: 30%;
  height: 2px;
  background-color: var(--platText-color);
}
.line::after {
  content: "";
  display: block;
  position: absolute;
  margin-top: 0.3rem;
  width: 100%;
  height: 2px;
  background-color: var(--platText-color);
}
.platImgText {
  display: none;
  position: absolute;
  justify-content: center;
  align-items: center;
  width: 100%;
  top: 20%;
  a {
    color: var(--platText-color);
  }
}
.platImgLeft:hover .platImgText,
.platImgRight:hover .platImgText {
  display: flex;
}
</style>