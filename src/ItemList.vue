<template>
  <div v-for="(a, i) in products" :key="i">
    <img :src="data[i].image" class="room-img" />
    <h4
        @click="$emit('openModal',data[i].id)"
    >
      {{ data[i].title }}
    </h4>
    <p>{{ data[i].price }}원</p>
  </div>
</template>

<script>
export default {
  name: "ItemList",
  props: {
    modalStatus: Boolean,
    statesNumber: Number,
    data: Object,
    products: Array,
  }
}
</script>

<style scoped>
.room-img {
  width: 100%;
  height: 30%
}

</style>