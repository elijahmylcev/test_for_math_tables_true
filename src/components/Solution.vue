<template>
  <div class="solution">
    <h2 v-if="currentTask == ''" class="solution__title">Выберите задание</h2>
    <h2 v-else>{{ currentTask }}</h2>
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

<style scoped lang="scss">

</style>