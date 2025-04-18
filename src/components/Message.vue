<script setup>
import { computed } from 'vue';

const props = defineProps(['result']);

const resultString = computed(() => {
  switch (props.result) {
    case 'win':
      return '你赢了！';
    case 'lose':
      return '你输了！';
    case 'draw':
      return '平局！';
    default:
      return '准备好了吗？选择你的武器！';
  }
});
</script>

<template>
  <div class="result" :class="result || 'draw'">
    {{ resultString }}
  </div>
</template>

<style scoped>
.result {
  text-align: center;
  padding: 15px;
  margin-top: 20px;
  border-radius: 8px;
  font-size: 20px;
  font-weight: bold;
}

.win {
  background-color: #e8f5e9;
  color: #2e7d32;
}

.lose {
  background-color: #ffebee;
  color: #c62828;
}

.draw {
  background-color: #fffde7;
  color: #f9a825;
}
</style>
