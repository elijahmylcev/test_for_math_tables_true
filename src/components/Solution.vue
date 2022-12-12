<template>
  <div class="solution">
    <div v-if="currentTask == ''">
      <h2 class="solution__title">Выберите задание</h2>
      <div class="circle">
        <div class="circle-u"></div>
      </div>

    </div>
    <div v-else>
      <h2>{{ currentTask }}</h2>
    </div>
  </div>
</template>

<script lang="js">
export default {
  name: 'Solution',
  props: {
    currentTask: String
  }
}
</script>

<style scoped>
.circle {
  margin: 15px auto;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100px;
  height: 100px;
  border-radius: 100%;
  border: 2px dashed rgba(30, 30, 209, .6);
  animation: rotate 1000ms infinite;
}

.circle-u {
  width: 85px;
  height: 85px;
  border-radius: 100%;
  border: 2px dashed rgba(7, 7, 92, 0.6);
  box-shadow: 1px 1px 15px rgba(30, 30, 209, .6);
  animation: rotate-u 800ms infinite;
}

@keyframes rotate-u {
  from {
    transform: rotate(-180deg);
  }

  to {
    transform: rotate(-360deg);
  }
}

@keyframes rotate {
  from {
    transform: rotate(180deg);
  }

  to {
    transform: rotate(360deg);
  }
}
</style>