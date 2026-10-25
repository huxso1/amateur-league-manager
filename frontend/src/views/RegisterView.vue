<script setup>
import { reactive, ref } from 'vue'
import { RouterLink } from 'vue-router'

const form = reactive({
  name: '',
  email: '',
  password: '',
  passwordConfirmation: '',
})

const message = ref('')
const error = ref('')

function handleSubmit() {
  message.value = ''
  error.value = ''

  if (form.password !== form.passwordConfirmation) {
    error.value = 'Пароли не совпадают.'
    return
  }

  message.value = 'Регистрационные данные готовы к отправке на сервер.'
}
</script>

<template>
  <section class="auth-section">
    <div class="auth-card">
      <div class="auth-header">
        <h1>Регистрация</h1>

        <p>
          Создайте аккаунт Serie A Fantasy
        </p>
      </div>

      <form class="auth-form" @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="name">
            Имя
          </label>

          <input
            id="name"
            v-model="form.name"
            type="text"
            placeholder="Введите имя"
            autocomplete="name"
            required
          >
        </div>

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
            autocomplete="new-password"
            minlength="6"
            required
          >
        </div>

        <div class="form-group">
          <label for="password-confirmation">
            Повторите пароль
          </label>

          <input
            id="password-confirmation"
            v-model="form.passwordConfirmation"
            type="password"
            placeholder="Повторите пароль"
            autocomplete="new-password"
            minlength="6"
            required
          >
        </div>

        <button class="auth-button" type="submit">
          Зарегистрироваться
        </button>

        <p v-if="error" class="form-error">
          {{ error }}
        </p>

        <p v-if="message" class="form-message">
          {{ message }}
        </p>
      </form>

      <p class="auth-link">
        Уже есть аккаунт?
        <RouterLink to="/login">
          Войти
        </RouterLink>
      </p>
    </div>
  </section>
</template>
