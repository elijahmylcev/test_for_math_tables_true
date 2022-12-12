<template>
  <div class="task_list">
    <div v-for="task in tasks" :key="task">
      {{ task }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'task_list',
  data() {
    return {
      tasks: ['1', '2', '3']
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>