<template>
  <div class="discount">
    <h4>지금 결제하면 {{salePercent}}% 할인</h4>
  </div>
</template>

<script>

export default {
  name: "TheDiscount",
  data(){
    return{
      salePercent : 30,
      showCount : true
    }
  },
  mounted(){
  const a= setInterval(()=>{
    this.salePercent--;
    if(this.salePercent == 0){
      clearInterval(a)
    }
  },1000);
    },


}
</script>

<style scoped>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius:5px
}
</style>