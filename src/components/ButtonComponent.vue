<template>
  <button class="shop-button">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'ButtonComponent',
  props: {
    text: {
      type: String,
      default: 'Shop Now →',
    },
  },
}
</script>

<style scoped>
.shop-button {
  background-color: #3bb77e;
  color: white;
  border: none;
  border-radius: 25px;
  padding: 10px 20px;
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.shop-button:hover {
  background-color: #2a9d6e;
}
</style>
