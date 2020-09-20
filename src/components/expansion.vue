<template>
  <div class="expansion">
    <div
      v-for="data in expandDatas"
      :key="data.id"
      class="expansionItem"
      :class="{overHidden : data.isexpansion}"
      @click="expand(data.id)"
    >
      <img :src="require(`../assets/${data.url}.jpg`)" :alt="data.info" />
      <a>{{data.info}}</a>
    </div>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      expandDatas: [
        {
          id: 0,
          url: "expansion-1",
          info: "Attractive",
          isexpansion: false
        },
        {
          id: 1,
          url: "expansion-2",
          info: "classic",
          isexpansion: false
        },
        {
          id: 2,
          url: "expansion-3",
          info: "lovely",
          isexpansion: false
        }
      ]
    };
  },
  methods: {
    expand(i) {
      if (this.expandDatas[i].isexpansion == true) {
        this.expandDatas[i].isexpansion = false;
      } else {
        for (let j = 0; j < this.expandDatas.length; j++) {
          this.expandDatas[j].isexpansion = false;
        }
        this.expandDatas[i].isexpansion = !this.expandDatas[i].isexpansion;
      }
    }
  }
};
</script>
<style scoped lang="scss">
.expansion {
  position: relative;
  overflow: hidden;
  margin-bottom: 5vw
}
.expansionItem {
  position: relative;
  height: 8vw;
  transition: ease 1s;
  padding: 1vw;
  img {
    max-width: 100%;
  }
  a{
    position: absolute;
    font-size: 6vw;
    left: 5%;
    color: #ffffff;
  }
}
.overHidden {
  height: 50vw !important;
}
</style>
