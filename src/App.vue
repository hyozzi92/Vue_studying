<template>
  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }}</a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div v-for="(a, i) in products" :key="i">
    <h4>{{ a }}</h4>
    <p>{{ price1[i] }}만원</p>
    <button @click="increase(i)">허위매물신고</button>
    <span>신고수 : {{ biolateNumber[i] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      biolateNumber: [0, 0, 0, 0],
      price1: [60, 70, 80],
      menu: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase(i) {
      this.biolateNumber[i]++;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
</style>
