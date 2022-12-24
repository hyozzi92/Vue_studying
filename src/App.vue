<template>
  <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <h4>{{ data[statesNumber].title }}</h4>
      <p>{{ data[statesNumber].price }}원</p>
      <img :src="data[statesNumber].image" />
      <button @click="modalStatus = false">닫기</button>
    </div>
    <div class="close-bg" @click="modalStatus = false"></div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }}</a>
  </div>
  <div v-for="(a, i) in products" :key="i">
    <img :src="data[i].image" class="room-img" />
    <h4
      @click="
        modalStatus = true;
        statesNumber = i;
      "
    >
      {{ data[i].title }}
    </h4>
    <p>{{ data[i].price }}원</p>
  </div>
</template>

<script>
console.log(data[0]?.tilte);
import data from "./data.js";

export default {
  name: "App",
  data() {
    return {
      statesNumber: 0,
      modalStatus: false,
      biolateNumber: [0, 0, 0, 0],
      price1: [60, 70, 80],
      menu: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      data: data,
    };
  },
  methods: {
    increase(i) {
      this.biolateNumber[i]++;
    },
    modalHandler() {},
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  display: flex;
  flex-direction: column;
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 2px;
}
.close-bg {
  width: 100%;
  height: 100%;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 100%;
}
</style>
