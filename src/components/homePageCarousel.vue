<template>
  <div class="homePage">
    <img class="carouselImg" src="../assets/ring1.jpeg" alt srcset align="center" />
    <img class="carouselImg" src="../assets/ring2.jpeg" alt srcset align="center" />
    <img class="carouselImg" src="../assets/ring3.jpeg" alt srcset align="center" />
    <img class="carouselImg" src="../assets/ring1.jpeg" alt srcset align="center" />
    <button style="z-index:10" @click="prev">prev</button>
    <button style="z-index:10" @click="next">next</button>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      timer: "",
      slides: document.getElementsByClassName("carouselImg"),
      slideIndex: 0
    };
  },
  methods: {
    next() {
      for (let i = 0; i < this.slides.length; i++) {
        this.slides[i].style.display = "none";
      }

      if (this.slides.length <= this.slideIndex) {
        this.slideIndex = 0;
      }

      for (let i = 0; i <= 2; i++) {
        if (this.slideIndex + i >= this.slides.length) {
          if (this.slideIndex + i == this.slides.length) {
            this.slides[0].style.left = `${100 * (i - 1)}%`;
            this.slides[0].style.display = "block";
          } else {
            this.slides[i - 1].style.left = `${100 * (i - 1)}%`;
            this.slides[i - 1].style.display = "block";
          }
        } else {
          this.slides[this.slideIndex + i].style.left = `${100 * i - 100}%`;
          this.slides[this.slideIndex + i].style.display = "block";

          console.log(this.slideIndex);
        }
      }
      this.slideIndex++;
    },
    prev() {
      this.slideIndex--;
      for (let i = 0; i < this.slides.length; i++) {
        this.slides[i].style.display = "none";
      }

      if (0 > this.slideIndex) {
        this.slideIndex = this.slides.length - 1
        console.log(this.slideIndex)
      }
      if(this.slideIndex-1<0){
          this.slides[this.slides.length-1].style.left = `-100%`;
          this.slides[this.slides.length-1].style.display = "block";
      }else{
          this.slides[this.slideIndex-1].style.left = `-100%`;
          this.slides[this.slideIndex-1].style.display = "block";
      }
      
      for (let i = 0; i < 2; i++) {
          if(this.slideIndex+i == this.slides.length){
              this.slides[0].style.left = '100%';
              this.slides[0].style.display = "block";
          } else {
              this.slides[this.slideIndex+i].style.left = `${100 * i}%`;
              this.slides[this.slideIndex+i].style.display = "block";
          }
      }
    },
  },
  mounted() {
    //自動播放 5秒一次
    //this.timer = setInterval(() => {
    //this.prev();
    //}, 5000);
    for (let i = 0; i < 2; i++) {
      this.slides[i].style.left = `${100 * i}%`;
      if(i+1 == this.slides.length){
          this.slides[i].style.left = `-100%`;
      }
      
    }
  },
  watch:{

  }
};
</script>
<style scoped lang="scss">
.homePage {
  display: flex;
  position: relative;
  align-items: center;
  width: 100%;
  overflow: hidden;
  height: 70vh;
  padding-top: 2rem;
  img {
    position: absolute;
    max-width: 100%;
    transition: all 3s ease;
  }
}
.homePage img:nth-child(1) {
  left: 0;
}
.homePage img:nth-child(2) {
  left: 100%;
}
.active {
  opacity: 0;
}
</style>