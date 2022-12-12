<template>
  <div class="task_list">
    <div v-for="task in tasks" :key="task">
      <task :task="task" />
    </div>
  </div>
</template>

<script>
import task from './task.vue'
export default {
  name: 'task_list',
  data() {
    return {
      tasks: ['( A ⇒ B ) ⇔ ¬A ∨ B',
        '¬( A ∨ B ) ⇔ ¬A ∧ ¬B',
        '¬( A ⇒ B ) ⇔ A ∧ ¬B',
        '( A ⇒ B ) ⇔ ( ¬B ⇒ ¬A )'
      ]
    }
  },
  components: {
    task: task
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.task_list {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  row-gap: 30px;
  align-items: flex-start;
}
</style>