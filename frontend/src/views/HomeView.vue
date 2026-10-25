<script setup>
import MatchCard from '../components/MatchCard.vue'

const upcomingMatches = [
  {
    id: 1,
    date: 'Тур 10',
    homeTeam: 'Inter',
    awayTeam: 'Napoli',
  },
  {
    id: 2,
    date: 'Тур 10',
    homeTeam: 'Juventus',
    awayTeam: 'Milan',
  },
]

const recentMatches = [
  {
    id: 3,
    date: 'Тур 9',
    homeTeam: 'Roma',
    awayTeam: 'Atalanta',
    score: '2 : 1',
  },
  {
    id: 4,
    date: 'Тур 9',
    homeTeam: 'Lazio',
    awayTeam: 'Fiorentina',
    score: '1 : 1',
  },
]
</script>

<template>
  <section class="matches-section">
    <h1>Ближайшие матчи</h1>

    <div class="matches-list">
      <MatchCard
        v-for="match in upcomingMatches"
        :key="match.id"
        :date="match.date"
        :home-team="match.homeTeam"
        :away-team="match.awayTeam"
      />
    </div>
  </section>

  <section class="matches-section">
    <h2>Последние результаты</h2>

    <div class="matches-list">
      <MatchCard
        v-for="match in recentMatches"
        :key="match.id"
        :date="match.date"
        :home-team="match.homeTeam"
        :away-team="match.awayTeam"
        :score="match.score"
      />
    </div>
  </section>
</template>

<style scoped>
.matches-section {
  margin-bottom: 40px;
}

.matches-section h1,
.matches-section h2 {
  margin-top: 0;
}

.matches-section h1 {
  font-size: 32px;
}

.matches-section h2 {
  font-size: 26px;
}

.matches-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

@media (max-width: 768px) {
  .matches-section h1 {
    font-size: 28px;
  }

  .matches-section h2 {
    font-size: 24px;
  }
}
</style>
