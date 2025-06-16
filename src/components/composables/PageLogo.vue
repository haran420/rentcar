<template>
  <router-link to="/" class="flex items-center gap-3 group transition duration-300 ease-in-out">
   
    <!-- Brand Text -->
    <h1 class="uppercase text-xl md:text-2xl font-bold tracking-wide font-serif shadow-sm group-hover:shadow-md transition duration-300 ease-in-out">
      <span :class="carClass" class="transition duration-300 ease-in-out">Car</span>
      <span class="text-green-800 group-hover:text-white-600 transition duration-300 ease-in-out">Book</span>
    </h1>
  </router-link>
</template>

<script>
import { computed, onBeforeUnmount, onMounted, ref } from 'vue'

export default {
  setup() {
    const isScrolled = ref(false)
    const isMobile = ref(window.innerWidth < 760)

    const handleScroll = () => {
      isScrolled.value = window.scrollY > 50
    }

    onMounted(() => {
      window.addEventListener('scroll', handleScroll)
    })

    onBeforeUnmount(() => {
      window.removeEventListener('scroll', handleScroll)
    })

    const carClass = computed(() => {
      if (isMobile.value) return "text-green-900"
      return isScrolled.value ? "text-green-900" : "text-white"
    })

    return {
      carClass
    }
  }
}
</script>

<style scoped>
/* Optional: Smooth shadow enhancement */
h1, .shadow-md {
  transition: box-shadow 0.3s ease;
}
</style>
