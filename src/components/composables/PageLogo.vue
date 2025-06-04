<template>
  <router-link to="/" class="flex items-center gap-1 group">
    <h1 class="uppercase text-xl md:text-2xl font-bold cursor-pointer tracking-wide transition duration-300 ease-in-out">
      <span :class="carClass" class="text-black group-hover:text-black-500 transition">Car</span>
      <span class="text-blue-500 group-hover:text-white transition">Book</span>
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
            if (isMobile.value) return "text-black"
            return isScrolled.value ? "text-black" : "text-white"
        })

        return {
            carClass
        }
    }
}
</script>

<style>

</style>