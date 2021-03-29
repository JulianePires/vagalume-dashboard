<template>
  <div class="container">
      <div class="login-area">
        <img src="../assets/logo-vagalume.png" alt="vagalume wi-fi"/>
        <form name="login" action="" method="post">
          <label class="form-label" for="username">Username</label>
          <input
            type="text"
            name="username"
            class="form-field"
            placeholder="Your username"
          />
          <label class="form-label" for="password">Password</label>
          <input
            type="password"
            name="password"
            class="form-field"
            placeholder="Your password"
          />
          <button class="form-button" id="login" type="submit">Enter</button>
        </form>
      </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  const axios = require("axios").default;

  const sendGetRequest = async () => {
      try {
        const resp = await axios.post("https://api.elcoma.com.br/api/visits/login", {
          body: {
            "username": "projetoselecao",
            "password": "Selec@o1",
          },
        });
        console.log(resp.data);
      } catch (err) {
        alert(err.message);
      }
    };

  export default Vue.extend({})
</script>

<style>

  .container {
    @apply bg-yellow-600 min-w-full min-h-screen;

    margin: 0 auto;

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;

    .login-area {
      @apply bg-gray-200 w-96 p-6 h-96 rounded-lg shadow-lg;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-evenly;

      img {
        @apply w-32 mb-6;
      }

      label {
        @apply text-gray-900;
        align-self: flex-start;
      }

      input {
        @apply text-gray-900 w-full my-3 h-9 px-2.5 rounded-md;

        &:focus {
          outline: none;
        }
      }

      button {
        @apply bg-gray-600 w-28 h-9 rounded-md mt-4 text-gray-200;
        transition: filter 0.2;

        &:hover {
          filter: brightness(0.9);
        }
      }
    }
  }

</style>
