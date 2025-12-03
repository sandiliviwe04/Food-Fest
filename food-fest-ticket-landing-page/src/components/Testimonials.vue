<template>
  <div class="testimonials">
    <h2>What Our Attendees Say</h2>
    <div class="testimonial-grid">
      <div v-for="testimonial in testimonials" :key="testimonial.name" class="testimonial">
        <p>{{ testimonial.quote }}</p>
        <p class="author">- {{ testimonial.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      testimonials: [
        {
          name: 'Ty Johnson',
          quote: 'The Cape Town Food Fest was an amazing experience! The food was delicious and the atmosphere was electric.',
        },
        {
          name: 'B Magobiyane',
          quote: 'I loved the variety of food stalls and the live music was fantastic. Can\'t wait for next year!',
        },
        {
          name: 'Ntsapo Tena',
          quote: 'The event was well-organized and the staff were friendly and helpful. Highly recommend!',
        }
      ],
    };
  },
};
</script>

<style scoped>
.testimonials {
  margin-bottom: 40px;
}

.testimonial-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.testimonial {
  background-color: #f7f7f7;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.author {
  font-weight: bold;
  margin-top: 10px;
}
</style>