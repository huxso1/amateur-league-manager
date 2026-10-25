<script setup>
import { ref } from 'vue'

const players = [
  {
    id: 1,
    name: 'Lautaro Martinez',
    team: 'Inter',
    position: 'Нападающий',
  },
  {
    id: 2,
    name: 'Christian Pulisic',
    team: 'Milan',
    position: 'Полузащитник',
  },
  {
    id: 3,
    name: 'Kenan Yildiz',
    team: 'Juventus',
    position: 'Нападающий',
  },
  {
    id: 4,
    name: 'Scott McTominay',
    team: 'Napoli',
    position: 'Полузащитник',
  },
]

const selectedPrediction = ref(null)

function selectPrediction(player, action) {
  selectedPrediction.value = {
    player: player.name,
    action,
  }
}
</script>

<template>
  <section class="fantasy-section">
    <div class="fantasy-header">
      <div>
        <span class="round-badge">Тур 10</span>

        <h1>Fantasy-прогноз</h1>

        <p>
          Выберите футболиста и спрогнозируйте его результативное действие.
        </p>
      </div>
    </div>

    <div class="fantasy-info">
      <div>
        <strong>Гол</strong>
        <span>+3 очка</span>
      </div>

      <div>
        <strong>Ассист</strong>
        <span>+2 очка</span>
      </div>
    </div>

    <h2>Игроки</h2>

    <div class="players-list">
      <article
        v-for="player in players"
        :key="player.id"
        class="player-card"
      >
        <div class="player-info">
          <div class="player-avatar">
            {{ player.name.charAt(0) }}
          </div>

          <div>
            <h3>{{ player.name }}</h3>

            <p>
              {{ player.team }} · {{ player.position }}
            </p>
          </div>
        </div>

        <div class="prediction-actions">
          <button
            type="button"
            @click="selectPrediction(player, 'Гол')"
          >
            Гол
          </button>

          <button
            type="button"
            @click="selectPrediction(player, 'Ассист')"
          >
            Ассист
          </button>
        </div>
      </article>
    </div>

    <div
      v-if="selectedPrediction"
      class="selected-prediction"
    >
      <span>Ваш прогноз:</span>

      <strong>
        {{ selectedPrediction.player }} —
        {{ selectedPrediction.action }}
      </strong>
    </div>
  </section>
</template>

<style scoped>
.fantasy-header {
  margin-bottom: 24px;
}

.fantasy-header h1 {
  margin: 12px 0 8px;

  font-size: 32px;
}

.fantasy-header p {
  margin: 0;

  color: var(--color-text-muted);
}

.round-badge {
  display: inline-block;

  padding: 6px 12px;

  color: var(--color-primary);
  background: rgba(23, 107, 255, 0.1);

  border-radius: 20px;

  font-size: 14px;
  font-weight: bold;
}

.fantasy-info {
  display: flex;
  gap: 16px;

  margin-bottom: 36px;
}

.fantasy-info div {
  display: flex;
  flex-direction: column;
  gap: 4px;

  min-width: 130px;

  padding: 16px 20px;

  background: var(--color-surface);

  border: 1px solid var(--color-border);
  border-radius: 12px;
}

.fantasy-info strong {
  color: var(--color-primary);
}

.fantasy-info span {
  color: var(--color-text-muted);

  font-size: 14px;
}

.fantasy-section h2 {
  margin-bottom: 18px;
}

.players-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.player-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 24px;

  padding: 20px 24px;

  background: var(--color-surface);

  border: 1px solid var(--color-border);
  border-radius: 12px;

  box-shadow: 0 4px 14px rgba(20, 40, 90, 0.07);
}

.player-info {
  display: flex;
  align-items: center;
  gap: 16px;
}

.player-avatar {
  width: 52px;
  height: 52px;

  flex-shrink: 0;

  display: flex;
  justify-content: center;
  align-items: center;

  color: #ffffff;

  font-size: 20px;
  font-weight: bold;

  background: linear-gradient(
    135deg,
    var(--color-primary),
    var(--color-violet)
  );

  border-radius: 50%;
}

.player-info h3 {
  margin: 0 0 6px;

  font-size: 18px;
}

.player-info p {
  margin: 0;

  color: var(--color-text-muted);

  font-size: 14px;
}

.prediction-actions {
  display: flex;
  gap: 10px;
}

.prediction-actions button {
  padding: 9px 16px;

  color: var(--color-primary);
  background: #ffffff;

  border: 1px solid var(--color-primary);
  border-radius: 8px;

  font: inherit;
  font-weight: 600;

  cursor: pointer;
}

.prediction-actions button:hover {
  color: #ffffff;
  background: var(--color-primary);
}

.selected-prediction {
  margin-top: 24px;
  padding: 18px 20px;

  display: flex;
  flex-direction: column;
  gap: 6px;

  background: linear-gradient(
    135deg,
    rgba(23, 107, 255, 0.1),
    rgba(108, 77, 255, 0.1)
  );

  border: 1px solid var(--color-primary);
  border-radius: 12px;
}

.selected-prediction span {
  color: var(--color-text-muted);

  font-size: 14px;
}

@media (max-width: 768px) {
  .fantasy-header h1 {
    font-size: 28px;
  }

  .fantasy-info {
    flex-direction: column;
  }

  .fantasy-info div {
    width: 100%;
  }

  .player-card {
    flex-direction: column;
    align-items: flex-start;
  }

  .prediction-actions {
    width: 100%;
  }

  .prediction-actions button {
    flex: 1;
  }
}
</style>
