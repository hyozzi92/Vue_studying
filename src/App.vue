<<<<<<< HEAD
<template>
<Modal @closeModal="modalStatus=false" :data="data" :statesNumber="statesNumber" :modalStatus="modalStatus"/>

  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }}</a>
  </div>

  <Discount/>

  <ItemList @openModal="modalStatus=true; statesNumber = $event" :modalStatus="modalStatus" :statesNumber="statesNumber" :data="data" :products="products" />

</template>

<script>
import data from "./data.js";
import Discount from "@/Discount";
import Modal from "./Modal"
import ItemList from "@/ItemList";

console.log(data)
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
  components: {ItemList, Discount, Modal},
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
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
=======
// src/components/TheNav.vue
// src/App.vue
<script setup>
import TheNav from './components/TheNav.vue';
import TheView from './components/TheView.vue';
</script>

<template>
  <TheNav></TheNav>

  <TheView></TheView>
  <AppCard></AppCard>

</template>
>>>>>>> 4bee2cbc26b554eaa131074a05f9d195c211f469
