<script setup>
defineProps(['playerChoice', 'computerChoice']);
</script>

<template>
  <div class="battle-area">
    <div class="player-side">
      <h3>你的选择</h3>
      <div class="choice-display">
        {{ playerChoice || '?' }}
      </div>
    </div>

    <div class="vs">VS</div>

    <div class="computer-side">
      <h3>电脑选择</h3>
      <div class="choice-display">
        {{ computerChoice || '?' }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.battle-area {
  display: flex;
  justify-content: space-between;
  margin-bottom: 40px;
}

.player-side,
.computer-side {
  text-align: center;
  width: 45%;
}

.choice-display {
  height: 120px;
  width: 120px;
  margin: 0 auto;
  background-color: #f9f9f9;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 50px;
  border: 3px solid #dddddd;
}

.vs {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  font-weight: bold;
  color: #ff5722;
}
</style>
