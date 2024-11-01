<template>
  <div
    class="flex justify-center items-center flex-wrap gap-10 pt-10 w-[1200px] m-auto"
  >
    <div
      v-for="(car, index) in cars"
      :key="index"
      class="w-[325px] bg-white rounded-[10px] shadow-lg overflow-hidden"
    >
      <div class="relative">
        <img
          :src="car.image"
          :alt="car.name"
          class="w-full h-[200px] object-cover"
        />
        <div
          v-if="car.available"
          class="absolute top-2 right-2 bg-green-500 text-white px-2 py-1 text-sm font-semibold rounded"
        >
          Доступен к заказу
        </div>
      </div>

      <div class="flex items-center mt-2 ml-4 text-gray-600">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-5 h-5 mr-1 text-gray-500"
          fill="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            d="M12 2a9 9 0 00-9 9 9 9 0 009 9 9 9 0 009-9 9 9 0 00-9-9zm0 16.2c-3.976 0-7.2-3.224-7.2-7.2S8.024 3.8 12 3.8s7.2 3.224 7.2 7.2-3.224 7.2-7.2 7.2zm0-12a4.8 4.8 0 104.8 4.8A4.8 4.8 0 0012 6.2zm0 7.6a2.8 2.8 0 112.8-2.8 2.8 2.8 0 01-2.8 2.8z"
          />
        </svg>
        <span>{{ car.mileage }} км</span>
      </div>

      <div class="px-4 pt-2 text-lg font-semibold flex items-center">
        <img :src="car.logo" alt="Car Logo" class="w-6 h-6 mr-2" />
        <span>{{ car.name }}</span>
      </div>

      <div class="flex justify-between px-4 py-2 text-gray-700">
        <div class="flex flex-col items-center">
          <span class="text-sm">Цена</span>
          <span class="text-red-500 font-bold text-lg">{{ car.price }} ₽</span>
        </div>
        <div class="flex flex-col items-center">
          <span class="text-sm">Год</span>
          <span class="font-medium text-lg">{{ car.year }}</span>
        </div>
        <div class="flex flex-col items-center">
          <span class="text-sm">Объем</span>
          <span class="font-medium text-lg">{{ car.engine }} см³</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { carList } from '@/mock/carList.js'
import axios from 'axios'
export default {
  name: 'CarCard',
  data() {
    return {
      cars: carList,
    }
  },
  methods: {
    async fetchCars() {
      try {
        const response = await axios.get('http://localhost:1337/api/cars', {
          headers: {
            Authorization: `27b429b5cdb6922c59855fc564ea30f36c9a395d8f55eddecaf7b13b108977b8333de473c25674fc76641c48005c3cab4d1403f56da9e3334491a40a458356995ff1855f7d6a70b46ddee3c2584f29bf4f67ad52a9aa430816f1f83acc7a1c6e88cfedcbe97cbcac630231436d8aa18bb9b0a69d4a35bf5de2f51706de6bc7e1`,
          },
        })
        console.log(response.data)
      } catch (error) {
        console.error(error)
      }
    },
  },
  mounted() {
    this.fetchCars()
  },
}
</script>

<style scoped>
/* Дополнительные стили при необходимости */
</style>
