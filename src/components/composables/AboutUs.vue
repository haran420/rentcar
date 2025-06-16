<template>
  <section class="bg-[#1f3d2e] py-16">
    <div class="max-w-6xl mx-auto px-4 flex flex-col md:flex-row items-center gap-6 md:gap-10 lg:gap-14">
      
      <!-- Image -->
      <div class="w-full md:w-1/2 flex justify-center">
        <img
          src="../../assets/images/reena.jpg"
          alt="About"
          class="max-w-sm md:max-w-md object-cover rounded-xl shadow-md"
        />
      </div>

      <!-- Content -->
      <div class="w-full md:w-1/2 text-white space-y-4">
        <h2 class="text-sm font-semibold uppercase tracking-wider">About Us</h2>
        <h1 class="text-3xl md:text-4xl font-bold">Welcome to Carbook</h1>
        <p class="text-base leading-relaxed">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum odit
          repellendus, odio atque ut nisi ea quia beatae deleniti dolores.
        </p>
        <p class="text-base leading-relaxed">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum odit
          repellendus, odio atque ut nisi ea quia beatae deleniti dolores.
        </p>
        <router-link to="/cars">
          <ButtonComponent text="Search Vehicle" />
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup>
import ButtonComponent from "./ButtonComponent.vue";
</script>
