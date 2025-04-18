<script setup>
import ScoreBoard from '@/components/ScoreBoard.vue';
import BattleArea from './components/BattleArea.vue';
import PlayerChoice from './components/PlayerChoice.vue';
import Message from './components/Message.vue';
import BattleHistory from './components/BattleHistory.vue';

import { reactive } from 'vue';

const scores = reactive({
  player: 0,
  computer: 0,
  draw: 0,
});
</script>

<template>
  <div class="container">
    <ScoreBoard :scores="scores"></ScoreBoard>
    <BattleArea></BattleArea>
    <PlayerChoice></PlayerChoice>
    <Message></Message>
    <BattleHistory></BattleHistory>
  </div>
</template>

<style scoped>
.container {
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  padding: 25px;
  width: 600px;
}
</style>
