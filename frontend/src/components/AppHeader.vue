<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <header class="app-header">
    <div class="header-content">
      <RouterLink class="logo" to="/">
        Serie A Fantasy
      </RouterLink>

      <nav>
        <RouterLink to="/">Главная</RouterLink>
        <RouterLink to="/teams">Команды</RouterLink>
        <RouterLink to="/fantasy">Fantasy</RouterLink>
      </nav>

      <RouterLink class="login-link" to="/login">
        Войти
      </RouterLink>
    </div>
  </header>
</template>

<style scoped>
.app-header {
  background: linear-gradient(
    135deg,
    var(--color-primary-dark),
    var(--color-primary)
  );

  border-bottom: 3px solid var(--color-accent);
}

.header-content {
  width: 100%;
  max-width: 1200px;

  margin: 0 auto;
  padding: 20px 40px;

  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  color: #ffffff;
  text-decoration: none;

  font-size: 24px;
  font-weight: bold;
}

nav {
  display: flex;
  align-items: center;
  gap: 28px;
}

nav a {
  padding: 8px 0;

  color: #ffffff;
  text-decoration: none;

  border-bottom: 2px solid transparent;
}

nav a:hover,
nav a.router-link-exact-active {
  color: var(--color-accent);
  border-bottom-color: var(--color-accent);
}

.login-link {
  display: inline-block;

  padding: 9px 18px;

  color: #ffffff;
  text-decoration: none;

  border: 1px solid #ffffff;
  border-radius: 8px;
}

.login-link:hover {
  color: var(--color-primary-dark);
  background: #ffffff;
}

@media (max-width: 768px) {
  .header-content {
    padding: 20px;

    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }

  nav {
    gap: 18px;
  }
}
</style>
