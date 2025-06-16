<template>
  <SectionHeading description="What we offer" title="Featured Vehicles" />

  <div class="relative w-full h-full py-10 md:py-20 flex justify-center">
    <!-- Custom navigation buttons -->
    <div class="swiper-button-prev custom-nav absolute top-1/2 -left-6 transform -translate-y-1/2 z-50"></div>
    <div class="swiper-button-next custom-nav absolute top-1/2 -right-6 transform -translate-y-1/2 z-50"></div>

    <swiper
      :modules="[Navigation, Autoplay]"
      :navigation="{
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev'
      }"
      :loop="true"
      :autoplay="{ delay: 3000, disableOnInteraction: false }"
      :space-between="30"
      :breakpoints="{
        640: { slidesPerView: 2 },
        1024: { slidesPerView: 3 }
      }"
      class="w-4/5 drop-shadow-2xl"
    >
      <swiper-slide v-for="(car, index) in cars" :key="index">
        <CarCard
          :id="car.id"
          :name="car.name"
          :brand="car.brand"
          :price="car.price"
          :image="car.image"
        />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Autoplay } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/autoplay";

import SectionHeading from "../composables/SectionHeading.vue";
import CarCard from "../cards/CarCard.vue";
import { cars } from "../../data/carsData";
</script>

<style scoped>
.custom-nav {
  width: 40px;
  height: 40px;
  background-color: white;
  border-radius: 9999px;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
