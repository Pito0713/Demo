<template>
  <div class="homePage" v-on:mouseover="stop" v-on:mouseout="play">
    <img class="carouselImg" src="../assets/new1.jpg" alt='newPost' srcset align="center" />
    <img class="carouselImg" src="../assets/new2.jpg" alt='new1' srcset align="center" />
    <img class="carouselImg" src="../assets/new3.jpg" alt='new2' srcset align="center" />
    <img class="carouselImg" src="../assets/new4.jpg" alt='new3' srcset align="center" />
    <div class="carouselButton" style="left:3%;" @click="prev">
      <i class="fas fa-chevron-left"></i>
    </div>
    <div class="carouselButton" style="z-index:10; right:3%;" @click="next">
      <i class="fas fa-chevron-right"></i>
    </div>
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
        this.slideIndex = this.slides.length - 1;
        console.log(this.slideIndex);
      }
      if (this.slideIndex - 1 < 0) {
        this.slides[this.slides.length - 1].style.left = `-100%`;
        this.slides[this.slides.length - 1].style.display = "block";
      } else {
        this.slides[this.slideIndex - 1].style.left = `-100%`;
        this.slides[this.slideIndex - 1].style.display = "block";
      }

      for (let i = 0; i < 2; i++) {
        if (this.slideIndex + i == this.slides.length) {
          this.slides[0].style.left = "100%";
          this.slides[0].style.display = "block";
        } else {
          this.slides[this.slideIndex + i].style.left = `${100 * i}%`;
          this.slides[this.slideIndex + i].style.display = "block";
        }
      }
    },
    play() {
      this.timer = setInterval(() => {
        this.next();
      }, 5000);
    },
    stop() {
      clearInterval(this.timer);
    }
  },
  mounted() {
    //自動播放 5秒一次
    this.timer = setInterval(() => {
    this.next();
    }, 5000);
    for (let i = 0; i < this.slides.length; i++) {
      this.slides[i].style.display = "none";
    }
    for (let i = 0; i < 2; i++) {
      this.slides[i].style.left = `${100 * i}%`;
      this.slides[i].style.display = "block";
      if (i + 1 == 2) {
        this.slides[this.slides.length - 1].style.left = "-100%";
        this.slides[this.slides.length - 1].style.display = "block";
      }
    }
  },
  watch: {}
};
</script>
<style scoped lang="scss">
.homePage {
  display: flex;
  position: relative;
  align-items: center;
  width: 100%;
  overflow: hidden;
  height: 80vh;
  padding-top: 2rem;
  margin-bottom: 5rem;
  img {
    position: absolute;
    max-width: 100%;
    transition: all 2s ease;
  }
  .carouselButton {
    position: absolute;
    z-index: 10;
  }
  i {
    font-size: 2rem;
    color: var(--bottom-color);
  }
  i:hover {
    color: #adb5bd;
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