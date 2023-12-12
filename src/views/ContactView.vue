<script setup>
import { ref } from "vue";

const name = ref("");
const email = ref("");
const message = ref("");

const sendMessageToDiscord = () => {
  const data = {
    embeds: [
      {
        author: {
          name: name.value,
        },
        title: email.value,
        description: message.value,

      }]
  }

  fetch(
    "https://discord.com/api/webhooks/1182481776015331368/bqTIG__3a9Qeibkq0bXC13eaej0D6VZR1Eeqc_W1YNu69LkC2dCNVbhS9A6yUiHCFpet",
    {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(data),
    }
  )
    .then((response) => {
      if (!response.ok) {
        throw new Error('Error sending data to Discord webhook');
      }
    })
    .catch((error) => {
      console.error(error);
    });
};

const resetForm = () => {
  name.value = "";
  email.value = "";
  message.value = "";
};

const handleSubmit = (e) => {
  e.preventDefault();
  sendMessageToDiscord();
  resetForm();
}

</script>

<template>
  <main>
    <h2>Nous contacter :</h2>
    <form @submit.prevent="handleSubmit">
      <label for="name">Nom : </label>
      <input type="text" id="name" v-model="name" required />
      <label for="email">Email : </label>
      <input type="text" id="email" v-model="email" required />
      <label for="message">Message : </label>
      <textarea id="message" v-model="message" cols="30" rows="10"></textarea>
      <button type="submit">Envoyer !</button>
    </form>
  </main>
</template>


<style>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

label {
  padding-top: 10px;
  padding-bottom: 10px;
  font-weight: bold;
}

button {
  appearance: none;
  background-color: #42b983;
  border: 1px solid black;
  border-radius: 6px;
  color: #fff;
  cursor: pointer;
  font-size: 14px;
  font-weight: 600;
  line-height: 20px;
  padding: 6px 16px;
  margin-top: 20px;
}
</style>
        