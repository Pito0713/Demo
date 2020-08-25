<template>
  <div class="model">
      <div class="modelBackground">
          <img src="../assets/model-1.jpg"  alt srcset />
      </div>
      <div class="modelborder"></div>
           <div class="modelShow">
          <img src="../assets/model-2.jpg"  alt srcset />
      </div>
      

      

  </div>
</template>

<script>
export default {};
</script>
<style scoped lang="scss">
.model{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: relative;
      img{
    max-width: 100%;
    }
}
.model::before{
      content: "Summer Side";
  display: block;
  position: absolute;
  border: 2px solid var(--border-color);
  width: 50%;
  height: 60%;
  top: -10%;
  transform: rotate(45deg);
  padding: 3%;
  z-index: -2;
}
.model::after{
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
.modelBackground{
    width: 50%;
    overflow: hidden;
    transform: rotate(45deg);
}

.modelBackground img {
    transform: rotate(-45deg) scale(1.5);
}
.modelShow{
    width: 35%;
    overflow: hidden;
    transform: rotate(45deg);
    top:100%;
    right: 25%

}
.modelShow img{
    
    transform: rotate(-45deg) scale(1.7);
}

</style>