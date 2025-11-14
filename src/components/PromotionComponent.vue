<template>
  <div class="promotion-card" :style="{ backgroundColor: bgColor }">
    <div class="promo-text">
      <h3>{{ title }}</h3>
      <button>{{ buttonText }} →</button>
    </div>
    <img :src="image" alt="" />
  </div>
</template>

<script>
export default {
  props: ['title', 'image', 'buttonText', 'bgColor']
}
</script>

<style scoped>
.promotion-card {
  flex: 1;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px 30px;
  border-radius: 16px;
  min-height: 180px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
}

.promo-text {
  max-width: 60%;
}

.promo-text h3 {
  font-size: 18px;
  font-weight: 600;
  color: #2b2b2b;
  margin-bottom: 15px;
}

.promo-text button {
  background-color: #00b074;
  color: white;
  border: none;
  border-radius: 8px;
  padding: 8px 18px;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.2s;
}

.promo-text button:hover {
  background-color: #00935f;
}

.promotion-card img {
  width: 120px;
  height: auto;
  object-fit: contain;
}
</style>
