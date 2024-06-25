<script> 
import PriceDisplay from './components/PriceDisplay.vue';

export default {
  components: {
    PriceDisplay
  }
};
</script>

<template>
    <div>
    <PriceDisplay :price="1000" />
    <PriceDisplay :price="5000" />
    <!-- Добавьте столько компонентов PriceDisplay, сколько нужно -->
  </div>
</template>

<style scoped>

</style>
