<template>
  <section class="py-10 md:py-16 bg-white">
    <!-- Heading -->
    <div class="text-center mb-12">
      <SectionHeading title="Our Latest Services" description="Services" />
    </div>

    <!-- Service Cards -->
    <div class="flex flex-wrap justify-center gap-8">
      <div
        v-for="(event, index) in events"
        :key="index"
        class="bg-white shadow-lg rounded-xl w-full md:w-64 p-6 text-center transition hover:shadow-2xl"
      >
        <!-- Icon -->
        <div class="flex justify-center mb-4">
          <div class="bg-blue-500 rounded-full w-16 h-16 flex items-center justify-center">
            <component :is="event.icon" class="text-white text-2xl" />
          </div>
        </div>

        <!-- Content -->
        <h2 class="text-lg font-semibold text-gray-800 mb-2">
          {{ event.title }}
        </h2>
        <p class="text-sm text-gray-500 mb-4">
          {{ event.description }}
        </p>

        <!-- Optional Button -->
        <button
          class="mt-auto text-sm font-medium text-blue-600 hover:underline focus:outline-none"
        >
          Find out more →
        </button>
      </div>
    </div>
  </section>
</template> 
<script setup>
import SectionHeading from "./SectionHeading.vue";
import { ref } from "vue";
import { AkHeart, IcCity, MaAirport } from "@kalimahapps/vue-icons";

const events = ref([
  {
    title: "Wedding Ceremony",
    description:
      "A small river named Duden flows by their place and supplies it with the necessary regelialia.",
    icon: AkHeart,
  },
  {
    title: "City Transfer",
    description:
      "A small river named Duden flows by their place and supplies it with the necessary regelialia.",
    icon: IcCity,
  },
  {
    title: "Airport Transfer",
    description:
      "A small river named Duden flows by their place and supplies it with the necessary regelialia.",
    icon: MaAirport,
  },
  {
    title: "Whole City Tour",
    description:
      "A small river named Duden flows by their place and supplies it with the necessary regelialia.",
    icon: IcCity,
  },
]);
</script>

<style scoped>
.card-hover:hover {
  transform: scale(1.02);
  transition: transform 0.3s ease;
}


</style>