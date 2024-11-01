<template>
  <div
    class="w-full h-[105px] bg-[#0f0900] flex items-center justify-between text-[#D4AF37] p-2"
  >
    <div class="font-bold text-2xl w-[100px] text-center">
      <router-link to="/">
        Capital Cars
      </router-link>
    </div>
    <div class="flex items-center justify-start text-base text-black ">
      <select class="" v-model="selectCity">
        <option v-for="city in cities" :key="city.id" :value="selectCity">
          {{ city.name }}
        </option>
      </select>
    </div>
    <div class="flex items-center gap-2.5">
      <BeakerIcon class="size-6"></BeakerIcon>
      <div class="hover:text-[#FFD54F]">telegram</div>
      <div class="hover:text-[#FFD54F]">WhatsApp</div>
      <div class="hover:text-[#FFD54F] ">8 (800) 700-18-94</div>
    </div>


    <div class="">
      <button class="btn bg-red-700 p-2 rounded-md">Заказать звонок</button>
    </div>
  </div>
</template>

<script >
import { BeakerIcon } from '@heroicons/vue/24/solid'
export default {
  name: 'HeaderDefault',
  components: {
    BeakerIcon,
  },
  data() {
    return {
      selectCity: 1,
      cities: [
        { id: 1, name: 'Москва' },
        { id: 2, name: 'Санкт-Петербург' },
        { id: 3, name: 'Новосибирск' },
        { id: 4, name: 'Екатеринбург' },
        { id: 5, name: 'Казань' },
      ],
    }
  },
}
</script>

<style scoped></style>
