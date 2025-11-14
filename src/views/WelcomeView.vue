<template>
  <div class="page-container">
    <!-- CATEGORY SECTION -->
    <div class="categories-container">
      <CategoryComponent
        v-for="category in categories"
        :key="category.name"
        :name="category.name"
        :image="category.image"
        :productCount="category.productCount"
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
import axios from "axios";
import CategoryComponent from '../components/CategoryComponent.vue'
import PromotionComponent from '../components/PromotionComponent.vue'
import ButtonComponent from '../components/ButtonComponent.vue'
export default {
  components: { CategoryComponent, PromotionComponent },

  data() {
    return {
      categories: [],
      promotions: [],
      
    };
  },

  methods: {
    async fetchPromotions() {
      try {
        const response = await axios.get('http://localhost:3000/api/promotions');
        this.promotions = response.data;
        console.log("Promotions:", this.promotions);
      } catch (error) {
        console.error("Error fetching promotions:", error);
      }
    },

    async fetchCategories() {
      try {
        const response = await axios.get('http://localhost:3000/api/categories');
        this.categories = response.data;
        console.log("Categories:", this.categories);
      } catch (error) {
        console.error("Error fetching categories:", error);
      }
    }
  },

  mounted() {
    this.fetchPromotions();
    this.fetchCategories();
  }
};
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
