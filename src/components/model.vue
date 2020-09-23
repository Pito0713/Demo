<template>
  <div class="model">
    <div class="modelBackground">
      <img src="../assets/model-1.jpg" alt srcset />
    </div>
    <div class="modelborder"></div>
    <div class="modelShow">
      <img src="../assets/model-2.jpg" alt srcset />
    </div>
  </div>
</template>

<script>
export default {};
</script>
<style scoped lang="scss">
.model {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: relative;
  margin-bottom: 20vw;
  img {
    max-width: 100%;
  }

}
.model::before {
  content: "Summer Side";
  display: block;
  position: absolute;
  border: 2px solid var(--border-color);
  width: 50%;
  height: 65%;
  top: -17%;
  transform: rotate(45deg);
  padding: 3%;
  z-index: -2;
  font-size: 4vw;
}
.model::after {
  content: "";
  display: block;
  position: absolute;
  border: 2px solid var(--border-color);
  width: 45%;
  height: 45%;
  top: 50%;
  transform: rotate(45deg);
  padding: 3%;
  z-index: 3;
}
.modelBackground {
  width: 50%;
  overflow: hidden;
  transform: rotate(45deg);
}

.modelBackground img {
  transform: rotate(-45deg) scale(1.5);
}
.modelShow {
  width: 35%;
  overflow: hidden;
  transform: rotate(45deg);
  top: 100%;
  right: 25%;
}
.modelborder::before{
  content: "";
  display: block;
  position: absolute;
  border-right: 1px solid var(--border-color);
  width: 10%;
  height: 50%;
  top: 70%;
  right: 20%;
  padding: 3%;
  z-index: 4;
  transform: rotate(45deg);
}
.modelborder::after{
  content: "";
  display: block;
  position: absolute;
  border-left: 1px solid var(--border-color);
  width: 10%;
  height: 60%;
  top: 60%;
  left: 20%;
  padding: 3%;
  z-index: 1;
}
.modelShow img {
  transform: rotate(-45deg) scale(1.7);
}
</style>