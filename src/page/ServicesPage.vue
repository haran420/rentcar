<template>
  <BgContainer
    title="Services"
    bgImage="two2.jpg"
    :links="[
      { text: 'Home', to: '/' },
      { text: 'Services', to: '/services' },
    ]"
  />
  <ServiceList />
  <CallToAction />
</template>

<script setup>
import BgContainer from "../components/composables/BgContainer.vue";
import ServiceList from "../components/composables/ServiceList.vue"
import CallToAction from "../components/composables/CallToAction.vue"
</script>

<style></style>