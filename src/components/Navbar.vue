<template>
  <nav class="nav">
    <div class="logo">
      <img src="../assets/logo.png" alt="logo" srcset="">
    </div>
    <div class="navBranch" :class="{ navOps: isOpen }">
      <ul>
        <li class="nav-Item">新品 New</li>
        <li class="nav-Item">耳環 Earrings</li>
        <li class="nav-Item">購物車 Cart</li>
        <li class="nav-Item">會員 mender</li>
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
      isOpen: false
    };
  },

  methods: {
    showUp() {
      this.isOpen = !this.isOpen;
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
}
.logo img{
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
  transform: translateX(200px)
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
  .navBranch{
    display: block;
    position: absolute;
    top:50px;
    /*hidden navbar*/
    left: -200px;
    height: 1000vh;
    transition: all 1s ease;
    border-right: 1px var(--border-color) solid;
  }
  .navBranch ul{
    flex-direction: column;
    .nav-Item {
      padding: 2rem;
    }
  }
}
</style>
