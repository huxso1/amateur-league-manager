<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <header>
    <div class="logo">
      <RouterLink to="/">Serie A Fantasy</RouterLink>
    </div>

    <nav>
      <RouterLink to="/">Главная</RouterLink>
      <RouterLink to="/teams">Команды</RouterLink>
    </nav>

    <div class="header-side-content">
      <RouterLink to="/login">Войти</RouterLink>
    </div>
  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 40px;
  background: #ffffff;
  border-bottom: 1px solid #dddddd;
}

.logo a {
  color: #202124;
  text-decoration: none;
  font-size: 22px;
  font-weight: bold;
}

nav {
  display: flex;
  gap: 24px;
}

nav a {
  color: #202124;
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}

.header-side-content a {
  display: inline-block;
  padding: 8px 14px;
  color: #202124;
  text-decoration: none;
  border: 1px solid #202124;
  border-radius: 6px;
}

.header-side-content a:hover {
  color: #ffffff;
  background: #202124;
}

@media (max-width: 768px) {
  header {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
    padding: 20px;
  }

  nav {
    gap: 16px;
  }
}
</style>
