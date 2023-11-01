<script setup>
import { ref } from 'vue';

let qty = ref(2) 

function addValue() {
 qty.value++
 console.log(qty)

}

function addValue1() {
  if(qty.value > 0){
    qty.value--
    console.log(qty)
  }
}
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="ballon" v-show="qty > 0">{{ qty }}</div>
    </div>

    <div class="button-wrapper">
      <div class="button" @click="addValue1" ><strong>-</strong></div>
      <div class="button" @click="addValue" ><strong>+</strong></div>
    </div>

    <div v-if="qty > 0" class="text">Me escribio 😎</div>
    <div v-else class="text"><strong>No me escribio 😭</strong></div>
  </div>
</template>

<style scoped>
.text{
  display: flex;
  justify-content: center;
}
.button {
  background-color: #a62b1f;
  display: inline-block;
  padding: 4px 0;
  border-radius: 4px;
  width: 32px;
  margin: 0 8px;
  cursor: pointer;
}

.button:hover {
  cursor: pointer;
  background-color: #520120;
  color: white;
}
.button-wrapper {
  text-align: center;
  margin-top: 16px;
  margin-bottom: 16px;
}
.ballon {
  width: 32px;
  height: 32px;
  background-color: red;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  position: absolute;
  top: 0;
  right: 0;
}
.profile {
  background-image: url('https://avatarfiles.alphacoders.com/244/244597.jpg');
  background-size: cover;
  width: 160px;
  height: 160px;
  margin: 0 auto;
  border-radius: 100%;
  position: relative;
}
.wrapper {
  padding-top: 18px;
  background-color: #1c646d;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
  overflow: hidden;
}
</style>
