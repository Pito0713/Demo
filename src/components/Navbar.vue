<template>
  <nav class="nav">
    <div class="logo">Logo</div>
    <div class="navBranch" :class="{ navOps: isOpen }">
      <ul>
        <li class="nav-Item">New</li>
        <li class="nav-Item">Earrings</li>
        <li class="nav-Item">Cart</li>
        <li class="nav-Item">mender</li>
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
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
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
  transform: translateX(100px)
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
    left: -100px;
    height: 10000vh;
    transition: all 1s ease;
  }
  .navBranch ul{
    flex-direction: column;
  }
}
</style>
