<template>
  <div class="page-container">
    <!-- CATEGORY SECTION -->
    <div class="categories-container">
      <CategoryComponent
        v-for="category in categories"
        :key="category.name"
        :name="category.name"
        :image="category.image"
        :items="category.items"
      />
    </div>

    <!-- PROMOTION SECTION -->
    <div class="promotions-container">
      <PromotionComponent
        v-for="promo in promotions"
        :key="promo.title"
        :title="promo.title"
        :image="promo.image"
        :buttonText="promo.buttonText"
        :bgColor="promo.bgColor"
      />
    </div>
  </div>
</template>

<script>
import CategoryComponent from '../components/CategoryComponent.vue'
import PromotionComponent from '../components/PromotionComponent.vue'

export default {
  components: { CategoryComponent, PromotionComponent },
  data() {
    return {
      categories: [
        { name: 'Cake & Milk', image: '/src/assets/Picture/burger.png', items: 14 },
        { name: 'Peach', image: '/src/assets/Picture/peach.png', items: 17 },
        { name: 'Organic Kiwi', image: '/src/assets/Picture/kiwi.png', items: 21 },
        { name: 'Red Apple', image: '/src/assets/Picture/apple.png', items: 68 },
        { name: 'Snack', image: '/src/assets/Picture/snack.png', items: 34 },
        { name: 'Black Plum', image: '/src/assets/Picture/plum.png', items: 25 },
        { name: 'Vegetables', image: '/src/assets/Picture/Vegetables.png', items: 65 },
        { name: 'Headphone', image: '/src/assets/Picture/headphone.png', items: 33 },
        { name: 'Cake & Milk', image: '/src/assets/Picture/Cake & Milk.png', items: 54 },
        { name: 'Orange', image: '/src/assets/Picture/orange.png', items: 63 },
      ],
      promotions: [
        {
          title: 'Everyday Fresh & Clean with Our Products',
          image: '/src/assets/Picture/onion.jpg',
          buttonText: 'Shop Now',
          bgColor: '#F3F0E9'
        },
        {
          title: 'Make your Breakfast Healthy and Easy',
          image: '/src/assets/Picture/juice.png',
          buttonText: 'Shop Now',
          bgColor: '#F8F3F8'
        },
        {
          title: 'The best Organic Products Online',
          image: '/src/assets/Picture/veggie.jpg',
          buttonText: 'Shop Now',
          bgColor: '#EEF3F7'
        }
      ]
    }
  }
}
</script>

<style scoped>
.page-container {
  display: flex;
  flex-direction: column;
  gap: 40px;
  padding: 30px 40px;
  background-color: white;
}

/* Top category section */
.categories-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: nowrap;
  gap: 20px;
  overflow-x: auto;
}

/* Bottom promotion section */
.promotions-container {
  display: flex;
  justify-content: space-between;
  gap: 25px;
  flex-wrap: nowrap;
}
</style>
