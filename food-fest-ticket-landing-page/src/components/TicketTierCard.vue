<template>
  <div class="ticket-tier-card" :class="{ featured: tier.featured }">
    <h2>{{ tier.name }}</h2>
    <p class="price">{{ tier.price }}</p>
    <ul class="benefits">
      <li v-for="benefit in tier.benefits" :key="benefit">{{ benefit }}</li>
    </ul>
    <button class="favourite-btn" @click="toggleFavourite">
      <span v-if="isFavourite">❤️</span>
      <span v-else>♡</span>
    </button>
  </div>
</template>

<script>
export default {
  props: {
    tier: Object,
  },
  data() {
    return {
      isFavourite: false,
    };
  },
  methods: {
    toggleFavourite() {
      this.isFavourite = !this.isFavourite;
    },
  },
};
</script>

<style scoped>
.ticket-tier-card {
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  margin: 20px;
  width: 300px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

.ticket-tier-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
}

.ticket-tier-card.featured {
  border-color: #ff9900;
  box-shadow: 0 0 20px rgba(255, 153, 0, 0.2);
  background-color: #fff7e6;
}

.price {
  font-size: 24px;
  font-weight: bold;
  color: #333;
}

.benefits {
  list-style: none;
  padding: 0;
  margin: 0;
}

.benefits li {
  margin-bottom: 10px;
  position: relative;
  padding-left: 20px;
}

.benefits li:before {
  content: "✔";
  position: absolute;
  left: 0;
  top: 0;
  color: #4CAF50;
}

.favourite-btn {
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
}

.favourite-btn:hover {
  transform: scale(1.2);
}
</style>