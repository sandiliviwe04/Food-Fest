<template>
  <div class="countdown-timer">
    <h2>Countdown to Cape Town Food Fest</h2>
    <p>{{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      eventDate: new Date('2026-03-07T10:00:00'),
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  },
  mounted() {
    setInterval(() => {
      const now = new Date();
      const diff = this.eventDate - now;
      this.days = Math.floor(diff / (1000 * 60 * 60 * 24));
      this.hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      this.minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      this.seconds = Math.floor((diff % (1000 * 60)) / 1000);
    }, 1000);
  },
};
</script>

<style scoped>
.countdown-timer {
  text-align: center;
  margin-bottom: 40px;
}
</style>