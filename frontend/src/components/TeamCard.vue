<script setup>
defineProps({
  name: {
    type: String,
    required: true,
  },
  abbreviation: {
    type: String,
    required: true,
  },
  city: {
    type: String,
    required: true,
  },
  stadium: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <article class="team-card">
    <div class="team-logo">
      {{ abbreviation }}
    </div>

    <div class="team-info">
      <h2>{{ name }}</h2>

      <p>{{ city }}</p>

      <span class="team-stadium">
        {{ stadium }}
      </span>
    </div>
  </article>
</template>

<style scoped>
.team-card {
  display: flex;
  align-items: center;
  gap: 20px;

  padding: 24px;

  background: var(--color-surface);

  border: 1px solid var(--color-border);
  border-radius: 12px;

  box-shadow: 0 4px 14px rgba(20, 40, 90, 0.08);

  transition:
    transform 0.2s ease,
    border-color 0.2s ease,
    box-shadow 0.2s ease;
}

.team-card:hover {
  transform: translateY(-2px);

  border-color: var(--color-primary);

  box-shadow: 0 7px 20px rgba(20, 40, 90, 0.13);
}

.team-logo {
  width: 64px;
  height: 64px;

  flex-shrink: 0;

  display: flex;
  justify-content: center;
  align-items: center;

  color: #ffffff;

  font-size: 16px;
  font-weight: bold;

  background: linear-gradient(
    135deg,
    var(--color-primary),
    var(--color-violet)
  );

  border-radius: 50%;
}

.team-info h2 {
  margin: 0 0 6px;

  font-size: 20px;
}

.team-info p {
  margin: 0 0 8px;

  color: var(--color-text-muted);
}

.team-stadium {
  color: var(--color-primary);

  font-size: 14px;
  font-weight: 600;
}

@media (max-width: 768px) {
  .team-card {
    padding: 20px;
  }

  .team-logo {
    width: 56px;
    height: 56px;
  }
}
</style>
