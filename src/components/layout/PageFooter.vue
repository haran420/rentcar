<template>
  <div
    ref="footerRef"
    class="bg-black text-white p-4 md:p-20 py-10 relative overflow-hidden"
    @mousemove="moveCursor"
    @mouseleave="hideCursor"
    @mouseenter="showCursor"
  >
    <!-- Custom Cursor --> 
    <div
      ref="cursorRef"
      class="pointer-events-none fixed w-12 h-12 rounded-full bg-white mix-blend-difference opacity-0 transition-opacity duration-300 transform -translate-x-1/2 -translate-y-1/2 z-50"
    ></div>

    <!-- Footer Content -->
    <div class="flex flex-col md:flex-row gap-10 justify-between">
      <!-- Logo and Description -->
      <div class="md:w-1/5 space-y-6">
        <h1 class="uppercase text-2xl font-bold cursor-pointer">
          <span class="text-white">Car</span><span class="text-green-500">Book</span>
        </h1>
        <p class="text-gray-300 text-base">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia
          sequi sed hic maxime amet earum.
        </p>
        <div class="flex items-center space-x-4 text-2xl">
          <FaBandsXTwitter class="cursor-pointer hover:text-green-400 transition" />
          <CgFacebook class="cursor-pointer hover:text-green-400 transition" />
          <BsInstagram class="cursor-pointer hover:text-green-400 transition" />
        </div>
      </div>

      <!-- Footer Links Sections -->
      <FooterLinks :title="'Information'" :links="informationLinks" />
      <FooterLinks :title="'Customer Support'" :links="customerSupportLinks" />

      <!-- Contact Information -->
      <div class="md:w-1/5 space-y-6">
        <h2 class="text-xl font-semibold">Have a Questions?</h2>
        <div class="flex flex-col space-y-4">
          <div
            v-for="(info, index) in contactInfo"
            :key="index"
            class="flex items-start space-x-3"
          >
            <component :is="info.icon" class="text-white text-xl" />
            <p class="text-gray-300 text-sm">{{ info.text }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer Bottom -->
    <div class="mt-16 text-center text-gray-400 text-sm">
      Copyright ©2025 ❤️ Code Designed and developed by Hariharan
    </div>
  </div>
</template>

<script setup>
import {
  BsInstagram,
  CgFacebook,
  FaBandsXTwitter,
  AkLocation,
  AnOutlinedMail,
  BsTelephoneFill,
} from "@kalimahapps/vue-icons";
import { ref } from "vue";
import FooterLinks from "../composables/FooterLinks.vue";

// Refs for cursor
const cursorRef = ref(null);
const footerRef = ref(null);

// Cursor movement
const moveCursor = (e) => {
  const cursor = cursorRef.value;
  if (!cursor) return;
  cursor.style.left = `${e.clientX}px`;
  cursor.style.top = `${e.clientY}px`;
  cursor.style.opacity = "1";
};

// Hide on leave
const hideCursor = () => {
  if (cursorRef.value) cursorRef.value.style.opacity = "0";
};
const showCursor = () => {
  if (cursorRef.value) cursorRef.value.style.opacity = "1";
};

// Links & Info
const informationLinks = [
  "About",
  "Services",
  "Terms and Conditions",
  "Best Price",
  "Guarantee",
  "Privacy & Cookies Policy",
];

const customerSupportLinks = [
  "FAQ",
  "Payment Option",
  "Booking Tips",
  "How it Works",
  "Contact Us",
];

const contactInfo = [
  {
    icon: AkLocation,
    text: "1046, Pagalavadi, Thuraiyur, Trichy, Tamil Nadu - INDIA",
  },
  { icon: AnOutlinedMail, text: "harivip147@gmail.com" },
  { icon: BsTelephoneFill, text: "9597547838" },
];


</script>

<style scoped>
/* Smooth hover effect for cursor over links (optional) */
a:hover {
  color: #10b981;
}
</style>