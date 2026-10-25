<script setup>
import { reactive, ref } from 'vue'
import { RouterLink } from 'vue-router'

const form = reactive({
  email: '',
  password: '',
})

const message = ref('')

function handleSubmit() {
  message.value = 'Данные формы готовы к отправке на сервер.'
}
</script>

<template>
  <section class="auth-section">
    <div class="auth-card">
      <div class="auth-header">
        <h1>Вход</h1>

        <p>
          Войдите в свой аккаунт Serie A Fantasy
        </p>
      </div>

      <form class="auth-form" @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="email">
            Email
          </label>

          <input
            id="email"
            v-model="form.email"
            type="email"
            placeholder="example@mail.com"
            autocomplete="email"
            required
          >
        </div>

        <div class="form-group">
          <label for="password">
            Пароль
          </label>

          <input
            id="password"
            v-model="form.password"
            type="password"
            placeholder="Введите пароль"
            autocomplete="current-password"
            required
          >
        </div>

        <button class="auth-button" type="submit">
          Войти
        </button>

        <p v-if="message" class="form-message">
          {{ message }}
        </p>
      </form>

      <p class="auth-link">
        Нет аккаунта?
        <RouterLink to="/register">
          Зарегистрироваться
        </RouterLink>
      </p>
    </div>
  </section>
</template>
