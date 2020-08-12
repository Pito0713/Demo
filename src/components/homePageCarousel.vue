<template>
  <div class="homePage">
    <img class="carouselImg" src="../assets/ring1.jpeg" alt srcset align="center" />
    <img class="carouselImg" src="../assets/ring2.jpeg" alt srcset align="center" />
    <img class="carouselImg" src="../assets/ring3.jpeg" alt srcset align="center" />
    <img class="carouselImg" src="../assets/ring2.jpeg" alt srcset align="center" />
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
    plusSpace() {
      for (let i = 0; i < this.slides.length; i++) {
        this.slides[i].style.display = "none";
        //this.slides[i].style=`z-index:0`
        //if(this.slideIndex < 2){
      }

      if (this.slides.length <= this.slideIndex) {
        this.slideIndex = 0;
      }
      
        
      
      for (let i = 0; i <= 2; i++) {
        if (this.slideIndex + i >= this.slides.length) {
            
          if (this.slideIndex + i == this.slides.length) {
            this.slides[0].style.left = `${100 * (i - 1)}%`;
            this.slides[0].style.display = "block";
            //this.slides[0].style=`z-index:${this.slides.length-i}`
            
          } else {
            this.slides[i - 1].style.left = `${100 * (i - 1)}%`;
            this.slides[i - 1].style.display = "block";
            //this.slides[i - 1].style=`z-index:${ i - 1 }`
          }
        } else {
          this.slides[this.slideIndex + i].style.left = `${100 * i - 100}%`;
          this.slides[this.slideIndex + i].style.display = "block";
          
          //this.slides[i].style=`z-index:${this.slides.length-i}`
          console.log(this.slideIndex)
        }
      }
      
      //this.slides[0].style.opacity= "0";
      this.slideIndex++;
      
      
      
      //this.slides[this.slideIndex].style.display = "block";
      //this.slides[this.slideIndex].style.order = "1";
    }
  },
  mounted() {
    //自動播放 5秒一次

    this.timer = setInterval(() => {
      this.plusSpace();
    }, 5000);
    for (let i = 0; i < this.slides.length; i++) {
      this.slides[i].style.left = `${100 * i}%`;
    }    
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