<template>
  <section
    class="bg-cover bg-center relative h-screen"
    :style="{ backgroundImage: `url(${bgImage})` }"
  >
    <!-- Overlay -->
    <div class="absolute inset-0 bg-black opacity-40"></div>

    <!-- Content -->
    <div class="relative z-20 flex items-center justify-center h-full text-center text-white px-4">
      <div class="w-full md:w-3/5 animate-fade-up space-y-6">
        
        <!-- Gradient Title -->
       <h1
         class="text-4xl md:text-6xl font-extrabold bg-gradient-to-r from-blue-800 via-pink-500 to-yellow-500 text-transparent bg-clip-text drop-shadow-[0_5px_20px_rgba(255,255,255,0.6)] whitespace-nowrap"
         >
         Fast & Easy Way To Rent Car
        </h1>

        <!-- Fancy Paragraph -->
        <p
          class="text-lg md:text-xl text-white drop-shadow-[0_2px_12px_rgba(255,255,255,0.5)] font-medium leading-relaxed tracking-wide"
        >
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequatur modi minus necessitatibus enim corporis, voluptatem sequi libero cum repellendus.
        </p>

        <!-- Glowing Subheading -->
        <h2
          class="text-3xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-blue-500 to-purple-500 drop-shadow-[0_0_20px_rgba(34,211,238,0.8)]"
        >
          Easy steps for renting a car
        </h2>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import bgImage from '../../assets/images/one.jpg'

const isVisible = ref(false)

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true
  }, 100)
})
</script>

<style scoped>
@keyframes fade-up {
  0% {
    opacity: 0;
    transform: translateY(40px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-up {
  animation: fade-up 1s ease-out;
}
</style>
