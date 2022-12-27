<template>
  <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <img class="modalImg" :src="data[statesNumber].image" />
      <h4>{{ data[statesNumber].title }}</h4>
      <p>{{ data[statesNumber].price }}원</p>

      <span> {{data[statesNumber].content}}</span>
      <Discount/>
      <button @click="$emit('closeModal')">닫기</button>

    </div>
    <div class="close-bg" @click="$emit('closeModal')"></div>
  </div>
</template>

<script>
export default {
  name: "TheModal.vue",
  props : {
    data : Object,
    statesNumber: Number,
    modalStatus : Boolean,
  },
}
</script>

<style scoped>
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
  justify-content: center;
  align-items: center;
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 2px;

}
.close-bg {
  width: 100%;
  height: 100%;
}
.modalImg{
  width : 50%;
  height: 50%;
}
</style>