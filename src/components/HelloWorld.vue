<template>
  <div class="login">
    <img src="../assets/logo.png" alt="" width="92" />
    <h3>Войдите В Админку!</h3>
    <div class="text">
      Используй логин "admin" и пароль "admin" что бы войти!
    </div>
    <div class="inputs">
      <v-text-field label="Логин" hide-details="auto"></v-text-field>
      <v-text-field
        label="Пароль"
        :rules="rules"
        hide-details="auto"
        type="password"
      ></v-text-field>
      <v-btn><router-link to="/about">Войти</router-link></v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => ({
    rules: [
      (value) => !!value || "Что-то пошло не так.",
      (value) => value === "admin",
    ],
  }),
};
</script>
<style>
.login {
  margin: 200px auto;
  padding: 100px;
  max-width: 500px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
.inputs {
  display: flex;
  flex-direction: column;
  row-gap: 30px;
}
</style>
