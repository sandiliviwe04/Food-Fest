<template>
  <div class="newsletter-signup">
    <h2>Stay Up-to-Date</h2>
    <form @submit.prevent="submitForm">
      <input type="email" v-model="email" placeholder="Enter your email address">
      <button type="submit">Subscribe</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
    };
  },
  methods: {
    submitForm() {
      // You'll need to replace this with your Mailchimp API endpoint and API key
      const apiEndpoint = 'https://your-mailchimp-api-endpoint.com';
      const apiKey = 'your-mailchimp-api-key';
      const listId = 'your-mailchimp-list-id';

      fetch(apiEndpoint, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          'Authorization': `Bearer ${apiKey}`,
        },
        body: JSON.stringify({
          email_address: this.email,
          status: 'subscribed',
          merge_fields: {},
        }),
      })
      .then(response => response.json())
      .then(data => {
        console.log(data);
      })
      .catch(error => {
        console.error(error);
      });
    },
  },
};
</script>

<style scoped>
.newsletter-signup {
  margin-bottom: 40px;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input[type="email"] {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 100%;
  max-width: 300px;
}

button[type="submit"] {
  padding: 10px 20px;
  background-color: #337ab7;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button[type="submit"]:hover {
  background-color: #23527c;
}
</style>