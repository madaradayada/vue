<template>
  <div>
  <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>
  <button type="button" @click="this.info = 'Some new'">Отправить</button>
  </div>
  <div>
    <PriceDisplay :price="1000" />
    <PriceDisplay :price="5000" />
    <!-- Добавьте столько компонентов PriceDisplay, сколько нужно -->
  </div>
</template>

<script>
import PriceDisplay from './components/PriceDisplay.vue'

export default {
  components: {
    PriceDisplay
  },
  data() {
    return {
      info: 'Title',
      someInfo: 'Anons of message'
    }
  }
}
</script>

<style scoped>
h3 { 
  font-weight: lighter; 
}

p {
color: red;
}
</style>
