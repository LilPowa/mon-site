<script setup>
import { ref } from 'vue';



const url = ref("");
const method = ref("GET");
const param = ref("");
const result = ref("")

const sendApiRequest = () => {
  fetch(url.value + '?' + param.value, {
    method: method.value,
    headers: {
      "Content-Type": "application/json",
    }
  })
    .then(async (response) => {
      if (!response.ok) {
        throw new Error('Error calling API');
      }
      const responseJSON = await response.json();
      result.value = responseJSON;
      document.getElementById("second-block").style.visibility = "visible";
      console.log(responseJSON);

    })
    .catch((error) => {
      console.error(error);
    });
}

const resetForm = () => {
  document.getElementById("second-block").style.visibility = "hidden";
  url.value = "";
  method.value = "";
  param.value = "";
};

const handleSubmit = (e) => {
  e.preventDefault();
  sendApiRequest();
  resetForm();
}

</script>

<template>
  <h2>Contacter une API GET :</h2>
  <div class="main">
    <div id="first-block">
      <form @submit.prevent="handleSubmit">
        <label for="url">URL :</label>
        <textarea id="url" v-model="url" cols="21" rows="3" required></textarea>
        <label for="method">Méthode :</label>
        <select name="method-option" id="method" v-model="method">
          <option value="GET">GET</option>
        </select>
        <label for="param">Paramètres :</label>
        <textarea id="param" v-model="param" cols="21" rows="3" required></textarea>
        <button>Envoyer !</button>
      </form>
    </div>
    <div id="second-block">
      <p style="font-weight: bold;">Résultat :</p>
      <div>{{ result }}</div>
    </div>
  </div>
</template>

<style>
.main {
  display: flex;
  justify-content: space-evenly;
}

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

#second-block {
  /* display: none; */
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