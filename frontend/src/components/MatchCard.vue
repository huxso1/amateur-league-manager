<script setup>
defineProps({
  date: {
    type: String,
    required: true,
  },
  homeTeam: {
    type: String,
    required: true,
  },
  awayTeam: {
    type: String,
    required: true,
  },
  score: {
    type: String,
    default: '',
  },
})
</script>

<template>
  <article class="match-card">
    <div class="match-date">
      {{ date }}
    </div>

    <div class="match-line">
      <span class="team team-home">
        {{ homeTeam }}
      </span>

      <strong v-if="score" class="match-score">
        {{ score }}
      </strong>

      <span v-else class="match-separator">
        —
      </span>

      <span class="team team-away">
        {{ awayTeam }}
      </span>
    </div>
  </article>
</template>

<style scoped>
.match-card {
  display: flex;
  justify-content: space-between;
  align-items: center;

  padding: 20px 24px;

  background: var(--color-surface);

  border: 1px solid var(--color-border);
  border-radius: 12px;

  box-shadow: 0 4px 14px rgba(20, 40, 90, 0.08);

  transition:
    transform 0.2s ease,
    border-color 0.2s ease,
    box-shadow 0.2s ease;
}

.match-card:hover {
  transform: translateY(-2px);

  border-color: var(--color-primary);

  box-shadow: 0 7px 20px rgba(20, 40, 90, 0.13);
}

.match-date {
  color: var(--color-text-muted);

  font-size: 14px;
  font-weight: bold;
}

.match-line {
  width: 520px;

  display: grid;
  grid-template-columns: minmax(140px, 1fr) 72px minmax(140px, 1fr);
  align-items: center;
  column-gap: 16px;

  font-size: 18px;
  font-weight: 500;
}

.team-home {
  text-align: right;
}

.team-away {
  text-align: left;
}

.match-score {
  justify-self: center;

  padding: 6px 10px;

  color: #ffffff;
  background: var(--color-primary);

  border-radius: 8px;
}

.match-separator {
  justify-self: center;

  color: var(--color-primary);
  font-weight: bold;
}

@media (max-width: 768px) {
  .match-card {
    flex-direction: column;
    align-items: stretch;
    gap: 12px;
  }

  .match-line {
    width: 100%;

    grid-template-columns: minmax(0, 1fr) 64px minmax(0, 1fr);

    font-size: 16px;
  }
}
</style>
