<template>
  <div class="app">
    <Header />
    <div class="ticket-tiers">
      <TicketTierCard v-for="tier in tiers" :key="tier.name" :tier="tier" />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import TicketTierCard from './components/TicketTierCard.vue';

export default {
  components: {
    Header,
    TicketTierCard,
  },
  data() {
    return {
      tiers: [
        {
          name: 'Bronze',
          price: 'R 499',
          benefits: ['Access to food stalls', '1 drink ticket'],
          featured: false,
        },
        {
          name: 'Silver',
          price: 'R 799',
          benefits: ['Access to food stalls', '2 drink tickets', 'Meet the chefs'],
          featured: true,
        },
        {
          name: 'Gold',
          price: 'R 1,299',
          benefits: ['Access to food stalls', 'Unlimited drinks', 'Meet the chefs', 'Exclusive access to VIP lounge'],
          featured: false,
        },
      ],
    };
  },
};
</script>

<style scoped>
.app {
  max-width: 1200px;
  margin: 40px auto;
  padding: 20px;
  background-color: #f2f2f2;
}

.ticket-tiers {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>