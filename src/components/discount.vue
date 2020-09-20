<template>
  <div class="discount">
    <a>Hot Sale 折扣</a>
    <img :src="require(`../assets/${url}`)"/>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      discount: [
        {
          dataurl: "discount-1.png",
          id: 0
        },
        {
          dataurl: "discount-2.png",
          id: 1
        }
      ],
      url:"discount-1.png",
      urlIndex: 0,
      timer:" "
    };
  },
  methods: {
    next() {
      return (this.url = this.discount[this.urlIndex].dataurl);
    }
  },
  watch: {
    urlIndex: function() {
      if (this.discount.length <= this.urlIndex) {
        return (this.urlIndex = 0);
      }
    }
  },
  mounted() {
    //自動播放 5秒一次
    this.timer = setInterval(() => {
      this.next();
      this.urlIndex++;
    }, 2000);
  }
};
</script>
<style scoped lang="scss">
.discount{
  
  margin-bottom: 5vw;
  a{
    position: relative;
    font-size: 8vw;
    float: left;
    padding-left: 10vw;
  }
  a::before{
    content: 'discount';
    font-size: 3vw;
    display: block;
    position: absolute;
    top:50%;
    right: -20%;
    width: 9vw;
    height: 1px;
    border-top: 2px solid var(--border-color);
  }
  img{
  max-width: 100%;
  }
}
</style>