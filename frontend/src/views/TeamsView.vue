<script setup>
import TeamCard from '../components/TeamCard.vue'

const teams = [
  {
    id: 1,
    name: 'Inter',
    abbreviation: 'INT',
    city: 'Milano',
    stadium: 'San Siro',
  },
  {
    id: 2,
    name: 'Milan',
    abbreviation: 'MIL',
    city: 'Milano',
    stadium: 'San Siro',
  },
  {
    id: 3,
    name: 'Juventus',
    abbreviation: 'JUV',
    city: 'Torino',
    stadium: 'Allianz Stadium',
  },
  {
    id: 4,
    name: 'Napoli',
    abbreviation: 'NAP',
    city: 'Napoli',
    stadium: 'Stadio Diego Armando Maradona',
  },
  {
    id: 5,
    name: 'Roma',
    abbreviation: 'ROM',
    city: 'Roma',
    stadium: 'Stadio Olimpico',
  },
  {
    id: 6,
    name: 'Atalanta',
    abbreviation: 'ATA',
    city: 'Bergamo',
    stadium: 'New Balance Arena',
  },
]
</script>

<template>
  <section class="teams-section">
    <div class="section-heading">
      <h1>Команды Serie A</h1>

      <p>
        Клубы, участвующие в нашем фэнтези-чемпионате.
      </p>
    </div>

    <div class="teams-list">
      <TeamCard
        v-for="team in teams"
        :key="team.id"
        :name="team.name"
        :abbreviation="team.abbreviation"
        :city="team.city"
        :stadium="team.stadium"
      />
    </div>
  </section>
</template>

<style scoped>
.section-heading {
  margin-bottom: 28px;
}

.section-heading h1 {
  margin: 0 0 8px;

  font-size: 32px;
}

.section-heading p {
  margin: 0;

  color: var(--color-text-muted);

  font-size: 16px;
}

.teams-list {
  display: grid;

  grid-template-columns: repeat(2, minmax(0, 1fr));

  gap: 20px;
}

@media (max-width: 768px) {
  .section-heading h1 {
    font-size: 28px;
  }

  .teams-list {
    grid-template-columns: 1fr;
  }
}
</style>
