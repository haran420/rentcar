<template>
  <div class="max-w-80 bg-white rounded-sm overflow-hidden shadow-md">
    <img :src="getImage(image)" alt="" class="w-full h-56 object-cover" />
    <div class="p-6 space-y-2">
      <h3 class="text-xl font-medium text-gray-800">{{ name }}</h3>
      <div class="flex justify-between items-center">
        <p class="text-md text-gray-400">{{ brand }}</p>
        <p class="text-md text-blue-500 font-semibold">
          {{ price }}
          <span class="text-gray-400 text-sm font-light">/day</span>
        </p>
      </div>

      <!-- Buttons: Light Brown Details, Green Book Now -->
      <div class="flex flex-row gap-3 pt-2 justify-center">
        <router-link :to="`/car/${id}`">
          <ButtonComponent text="Details" bgColor="bg-amber-200 text-gray-800" />
        </router-link>
        <router-link :to="`/pricing`">
          <ButtonComponent text="Book Now" bgColor="bg-green-600 text-white" />
        </router-link>
      </div>
    </div>
  </div>
</template>

<script setup>
import ButtonComponent from "../composables/ButtonComponent.vue";
defineProps({
  id: Number,
  name: String,
  brand: String,
  price: String,
  image: String,
});

const getImage = (imageName) => {
  return new URL(`/src/assets/images/${imageName}`, import.meta.url).href;
};
</script>

<style></style>