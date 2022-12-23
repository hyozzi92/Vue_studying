<template>
  <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modalStatus = false">닫기</button>
    </div>
    <div class="close-bg" @click="modalStatus = false"></div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }}</a>
  </div>
  <div v-for="(a, i) in products" :key="i">
    <img :src="data[i].image" class="room-img" />
    <h4>{{ data[i].title }}</h4>
    <p>{{ data[i].price }}원</p>
  </div>
</template>

<script>
import data from "./data.js";

export default {
  name: "App",
  data() {
    return {
      modalStatus: false,
      biolateNumber: [0, 0, 0, 0],
      price1: [60, 70, 80],
      menu: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      imgName: [
        require("./assets/room0.jpg"),
        require("./assets/room1.jpg"),
        require("./assets/room2.jpg"),
      ],
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
