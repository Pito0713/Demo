<template>
  <div class="homePage">
    <img id="carouselImg" src="../assets/ring1.jpeg" alt srcset align="center" />
    <img id="carouselImg" src="../assets/ring2.jpeg" alt srcset align="center" />
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      timer: "",
    };
  },
  methods: {
    plusSpace() {
      let carouselImg = document.documentElement.querySelectorAll(
        "#carouselImg"
      );

      for (let i = 0; i < carouselImg.length; i++) {
        carouselImg[carouselImg.length - 1].style.display = "none";
        //只能用let使用完即丟 不能用var 全域定義
        setTimeout(function() {
          carouselImg[i].style.display = "block";
          if (i > 0) {
            carouselImg[i - 1].style.display = "none";
          }
        }, 2000 * i);
      }
    }
  },
  mounted() {
    //自動播放 5秒一次
    let carouselImg = document.documentElement.querySelectorAll("#carouselImg");
    this.plusSpace();
    this.timer = setInterval(() => {
      this.plusSpace();
    }, carouselImg.length * 2000);
  }
};
</script>
<style scoped lang="scss">
.homePage {
  display: flex;
  align-items: center;
  width: 100%;
  overflow: hidden;
  height: 300px;
  img {
    max-width: 100%;
  }
}
#carouselImg {
  display: none;
}
</style>