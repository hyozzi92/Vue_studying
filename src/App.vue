
<template>

  <transition name="fade">
<Modal @closeModal="modalStatus=false" :data="data" :statesNumber="statesNumber" :modalStatus="modalStatus"/>
  </transition>
  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }}</a>
  </div>

  <Discount />
  <button @click="priceSort">가격순 정렬</button>
  <button @click="sortBack">되돌리기</button>

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
      showDiscount : true,
      originalData : [...data],
      statesNumber: 0,
      modalStatus: false,
      biolateNumber: [0, 0, 0, 0],
      price1: [60, 70, 80],
      menu: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      data: data,
    };
  },

  mounted(){

  },
  methods: {
    increase(i) {
      this.biolateNumber[i]++;
    },
    priceSort(){
      this.data.sort((a,b)=>{return  b.price - a.price })
    },
    sortBack(){
      this.data = [...this.originalData]
    }
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
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to{
  opacity: 1;
}

</style>



