<template>
  <div>
    <span v-if="discountedPrice !== price" class="old-price">{{ formattedPrice(price) }}</span>
    <span class="new-price">{{ formattedPrice(discountedPrice) }}</span>
  </div>
</template>

<script>
export default {
  props: {
    price: {
      type: Number,
      required: true
    },
    discount: {
      type: Number,
      default: 20 // Процент скидки по умолчанию
    }
  },
  computed: {
    discountedPrice() {
      return this.price - (this.price * this.discount) / 100
    }
  },
  methods: {
    formattedPrice(value) {
      return new Intl.NumberFormat('ru-RU', { style: 'currency', currency: 'UAH' }).format(value)
    }
  }
}
</script>

<style scoped>
.old-price {
  text-decoration: line-through;
  color: #040404;
  font-family: Ubuntu;
  font-size: 12px;
  font-weight: 400;
  line-height: 15.6px;
  text-align: left;
}

.new-price {
  color: #040404;
  font-family: Ubuntu;
  font-size: 20px;
  font-weight: 700;
  line-height: 22.98px;
  text-align: left;
}
</style>
