<template>
  <div class="flex flex-col h-full bg-white shadow-md p-4 rounded">
    <!-- Image -->
    <img
      :src="getImage(image)"
      alt=""
      class="object-cover h-56 w-full rounded"
    />

    <!-- Body -->
    <div class="flex flex-col justify-between flex-1 pt-5">
      <!-- Top: Text Content -->
      <div>
        <p class="text-sm text-blue-500 mb-2">
          {{ date }} {{ author }} {{ comments?.length }} comments
        </p>
        <h2 class="text-xl font-medium text-gray-800">
          {{ title }}
        </h2>
      </div>

      <!-- Bottom: Button -->
      <div class="mt-4">
        <router-link :to="`/blog/${id}`">
          <ButtonComponent text="Read More" />
        </router-link>
      </div>
    </div>
  </div>
</template>
<script setup>
import ButtonComponent from "../composables/ButtonComponent.vue";

defineProps({
  id: Number,
  title: String,
  author: String,
  comments: Number,
  date: String,
  image: String,
  imageHeight: { type: String, default: "h-56" },
});

const getImage = (imageName) => {
  return new URL(`/src/assets/images/${imageName}`, import.meta.url).href;
};
</script>

<style></style>