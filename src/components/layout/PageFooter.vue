<template>
  <div
    ref="footerRef"
    class="bg-[#1f3d2e] text-white px-4 md:px-16 py-10 shadow-[0_-5px_20px_rgba(0,0,0,0.3)] relative"
    @mousemove="moveCursor"
    @mouseleave="hideCursor"
    @mouseenter="showCursor"
  >
    <!-- Custom Cursor -->
    <div
      ref="cursorRef"
      class="pointer-events-none fixed w-10 h-10 rounded-full bg-white mix-blend-difference opacity-0 transition-opacity duration-300 transform -translate-x-1/2 -translate-y-1/2 z-50"
    ></div>

    <!-- Main Footer Content -->
    <div class="flex flex-col md:flex-row gap-10 justify-between text-sm">
      <!-- Logo and About -->
      <div class="md:w-1/5 space-y-3">
        <h1 class="text-3xl font-extrabold uppercase tracking-wider">
         <span class="text-white drop-shadow-[1px_1px_2px_rgba(0,0,0,0.5)]">CAR</span>
         <span class="text-green-400 drop-shadow-[0_0_6px_rgba(34,197,94,0.8)] ml-1">BOOK</span>
        </h1>
        <p class="text-gray-300 leading-relaxed text-sm">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia sequi sed hic maxime amet earum.
        </p>
        <div class="flex gap-3 text-lg text-gray-300 pt-2">
          <FaBandsXTwitter class="hover:text-green-300 cursor-pointer" />
          <CgFacebook class="hover:text-green-300 cursor-pointer" />
          <BsInstagram class="hover:text-green-300 cursor-pointer" />
        </div>
      </div>

      <!-- Info & Support -->
      <FooterLinks :title="'Information'" :links="informationLinks" />
      <FooterLinks :title="'Customer Support'" :links="customerSupportLinks" />

      <!-- Contact Info -->
      <div class="md:w-1/5 space-y-3">
        <h2 class="text-xl font-semibold text-white">Have a Questions?</h2>
        <div class="space-y-3 text-sm text-gray-300">
          <div
            v-for="(info, index) in contactInfo"
            :key="index"
            class="flex items-start gap-3"
          >
            <div class="bg-green-300 text-green-900 p-2 rounded-full">
              <component :is="info.icon" class="text-base" />
            </div>
            <p>{{ info.text }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom Line -->
    <div class="text-center text-gray-400 text-xs mt-8 pt-4 border-t border-gray-600">
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