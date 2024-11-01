<script setup>
import HeaderDefault from '@/components/Layouts/HeaderDefault.vue'
import CarsList from '@/components/CarsCard.vue'
</script>

<template>
  <div class="app">
    <HeaderDefault />

    <main class="item flex">
      <div class="items_1">1</div>
      <div class="items_2">2</div>
      <div class="items_3">3</div>
      <div class="items_4">4</div>
      <div class="items_5">5</div>
    </main>
    <CarsList />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
}
.app {
}

.items_2 {
  width: 200px;
  height: 200px;
  background-color: #FFF8E7;
}
.items_3 {
  width: 200px;
  height: 200px;
  background: rgb(17,54,40);
  background: linear-gradient(90deg, rgba(17,54,40,1) 0%, rgba(0,120,5,0.6111694677871149) 100%);
}
.items_4 {
  width: 200px;
  height: 200px;
  background-color: #D4AF37;
}
.items_5 {
  width: 200px;
  height: 200px;
  background-color: #FFD54F;
}
</style>
