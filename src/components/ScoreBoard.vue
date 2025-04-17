<script setup></script>

<template>
  <div class="score-board">
    <div class="score">
      <h3>玩家</h3>
      <p>0</p>
    </div>
    <div class="score">
      <h3>平局</h3>
      <p>0</p>
    </div>
    <div class="score">
      <h3>电脑</h3>
      <p>0</p>
    </div>
  </div>
</template>

<style scoped>
.score-board {
  display: flex;
  justify-content: space-between;
  margin-bottom: 30px;
  padding: 15px;
  background-color: #f0f0f0;
  border-radius: 8px;
}

.score {
  text-align: center;
  flex: 1;
}

.score h3 {
  margin: 5px 0;
  color: #555555;
}

.score p {
  font-size: 24px;
  font-weight: bold;
  margin: 5px 0;
  color: #333333;
}
</style>
