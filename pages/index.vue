<template>
  <main class="container">
      <AppHeader />
      <AppRestaurantInfo />
  </main>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue';
import AppRestaurantInfo from '@/components/AppRestaurantifo.vue'

export default {
  components: {
    AppHeader,
    AppRestaurantInfo
  },
};
</script>

<style>
</style>
