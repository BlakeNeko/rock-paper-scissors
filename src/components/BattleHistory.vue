<script setup>
defineProps(['history']);

function getEachRoundResultString(result) {
  switch (result) {
    case 'win':
      return '胜';
    case 'lose':
      return '负';
    case 'draw':
      return '平';
  }
}
</script>

<template>
  <div class="history">
    <h3>对战历史</h3>
    <div class="round-history">
      <div v-for="(item, index) in history" :key="index" class="round">
        <div>回合{{ item.round }}</div>
        <div>{{ item.player }} vs {{ item.computer }}</div>
        <div>
          {{ getEachRoundResultString(item.result) }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.history {
  margin-top: 30px;
}

.history h3 {
  text-align: center;
  margin-bottom: 10px;
}

.round-history {
  display: flex;
  overflow-x: auto;
  padding: 10px 0;
}

.round {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  padding: 8px;
  margin: 0 5px;
  border-radius: 5px;
  background-color: #f5f5f5;
  min-width: 90px;
}
</style>
