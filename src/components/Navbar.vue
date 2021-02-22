<template>
  <nav class="nav" id="nav">
    <a class="logo"  href='https://pito0713.github.io/Demo/'>
      <img src="../img/logo.png" alt="logo" />
    </a>
    <div class="navBranch" :class="{ navOps: isOpen }">
      <ul>
        <li class="nav-Item">
          <a href="https://pito0713.github.io/earIngProudct">耳環 Earrings</a>
        </li>
        <li class="nav-Item">
          <a href="https://pito0713.github.io/carcartEaring/"
          >購物車 Cart</a>
        </li>
      </ul>
    </div>
    <!--Navburger-->
    <div class="burger" @click="showUp">
      <div class="burgerLine"></div>
      <div class="burgerLine"></div>
      <div class="burgerLine"></div>
    </div>
  </nav>
</template>

<script>
export default {
  data: function() {
    return {
      isOpen: false,
      scrollTop: "",
    };
  },
  methods: {
    showUp() {
      this.isOpen = !this.isOpen;
    }
  },
  mounted() {
    var _this = this;
    window.onscroll = function() {
      _this.scrollTop =
        document.documentElement.scrollTop || document.body.scrollTop;
    };
  },
  watch: {
    scrollTop: function() {
      var nav = document.getElementById("nav");
      var navHeight = nav.offsetHeight;
      if (this.scrollTop > navHeight / 2) {
        nav.style.position = "fixed";
        nav.style.backgroundColor = "var(--background-color)";
      } else {
        nav.style.position = "relative";
        nav.style.backgroundColor = "#ffffff";
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: calc(100% - 4vw);
  top: 0;
  left: 0;
  z-index: 10;
  padding: 0 2vw;
}
.logo{
  display:flex;
  align-items: center;
  margin: 0.7rem;
}
.logo img {
  width: 60px;
}
.navBranch ul {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.navBranch .nav-Item {
  padding: 0 1rem;
}
.navOps {
  /*show navbar*/
  transform: translateX(250px);
}
/*-burger-*/
.burger {
  display: none;
}
.burger div {
  width: 20px;
  height: 2px;
  position: relative;
  display: block;
  background-color: #000000;
  margin: 4px 0;
}

@media screen and (max-width: 769px) {
  .burger {
    display: block;
  }
  .navBranch {
    display: block;
    position: fixed;
    top: 82px;
    /*hidden navbar*/
    left: -250px;
    height: 100%;
    transition: all 1s ease;
    border-right: 1px var(--border-color) solid;
    z-index: 1;
    background-color: var(--background-color);
    width: 30%;
  }
  .navBranch ul {
    flex-direction: column;
    .nav-Item {
      padding: 2rem;
    }
  }
}
</style>
