<template>
  <div class="category-card">
    <img :src="getImage(image)" alt="" />
    <h3>{{ name }}</h3>
    <p>{{ productCount }} items</p>
  </div>
</template>

<script>
export default {
  props: ['name', 'image', 'productCount'],

  methods: {
    getImage(path){
      return `http://localhost:3000/${path.replace(/\\/g, '/')}`;
    }
  } 
}

</script>

<style scoped>
.category-card {
  width: 120px;
  height: 130px;
  background: #fff;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 1px 4px rgba(0,0,0,0.08);
  padding: 10px;
  transition: all 0.2s ease-in-out;
  cursor: pointer;
}

.category-card:hover {
  border: 2px solid #a3d4a0;
  transform: translateY(-3px);
}

.category-card img {
  width: 50px;
  height: 50px;
  object-fit: contain;
  margin-top: 5px;
}

.category-card h3 {
  font-size: 14px;
  font-weight: 600;
  color: #333;
  margin-top: 10px;
}

.category-card p {
  font-size: 12px;
  color: #999;
  margin-top: 4px;
}
</style>
