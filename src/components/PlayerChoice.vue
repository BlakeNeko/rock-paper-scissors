<script setup>
const emit = defineEmits(['choice']);

function handleClick(choice) {
  emit('choice', choice);
}
</script>

<template>
  <div class="player-choices">
    <button class="choice-btn" @click="handleClick('✊')">✊</button>
    <button class="choice-btn" @click="handleClick('✋')">✋</button>
    <button class="choice-btn" @click="handleClick('✌️')">✌️</button>
  </div>
</template>

<style scoped>
.player-choices {
  display: flex;
  justify-content: space-around;
  margin-top: 30px;
}

.choice-btn {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  border: none;
  background-color: white;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
  font-size: 30px;
  cursor: pointer;
  transition: transform 0.2s, box-shadow 0.2s;
}

.choice-btn:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.15);
}
</style>
