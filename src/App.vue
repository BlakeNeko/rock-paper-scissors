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

const gameState = reactive({
  playerChoice: null,
  computerChoice: null,
  result: null,
});

const gameHistory = reactive([]);

function makeComputerChoice() {
  const choices = ['✊', '✋', '✌️'];
  const randomIndex = Math.floor(Math.random() * choices.length);
  return choices[randomIndex];
}

function determineWinner(playerChoice, computerChoice) {
  if (playerChoice === computerChoice) {
    return 'draw';
  }

  if (
    (playerChoice === '✊' && computerChoice === '✌️') ||
    (playerChoice === '✋' && computerChoice === '✊') ||
    (playerChoice === '✌️' && computerChoice === '✋')
  )
    return 'win';
  else {
    return 'lose';
  }
}

function handlePlayerChoice(choice) {
  gameState.playerChoice = choice;
  gameState.computerChoice = makeComputerChoice();
  gameState.result = determineWinner(
    gameState.playerChoice,
    gameState.computerChoice
  );

  // 更新比分
  switch (gameState.result) {
    case 'win':
      scores.player++;
      break;
    case 'lose':
      scores.computer++;
      break;
    default:
      scores.draw++;
      break;
  }

  // 记录历史
  // 添加到数组最前面，这样展示的时候最左侧就一直是最新的结果
  gameHistory.unshift({
    round: gameHistory.length + 1,
    player: gameState.playerChoice,
    computer: gameState.computerChoice,
    result: gameState.result,
  });
}
</script>

<template>
  <div class="container">
    <ScoreBoard :scores="scores"></ScoreBoard>
    <BattleArea
      :player-choice="gameState.playerChoice"
      :computer-choice="gameState.computerChoice"
    ></BattleArea>
    <PlayerChoice @choice="handlePlayerChoice"></PlayerChoice>
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
