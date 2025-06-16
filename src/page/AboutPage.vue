<template>
  <BgContainer
    title="About"
    bgImage="two2.jpg"
    :links="[
      { text: 'Home', to: '/' },
      { text: 'About Us', to: '/about' },
    ]"
  />
  <br><br>
  <AboutUs/><br><br>
  <CallToAction/>
  <TestimonySection/>
  <StatisticsSection/>
</template>

<script setup>
import BgContainer from "../components/composables/BgContainer.vue";
import AboutUs from "../components/composables/AboutUs.vue"
import CallToAction from "../components/composables/CallToAction.vue";
import TestimonySection from "../components/homePage/TestimonySection.vue";
import StatisticsSection from "../components/composables/StatisticsSection.vue";
</script>

<style></style>