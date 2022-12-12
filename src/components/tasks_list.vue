<template>
  <div class="task_list">
    <div v-for="task in tasks" :key="task">
      <task :task="task" @click="toUp" />
    </div>
  </div>
</template>

<script>
import task from './task.vue'
export default {
  name: 'task_list',
  data() {
    return {
      tasks:
        [
          '( A ⇒ B ) ⇔ ¬A ∨ B',
          '¬( A ∨ B ) ⇔ ¬A ∧ ¬B',
          '¬( A ⇒ B ) ⇔ A ∧ ¬B',
          '( A ⇒ B ) ⇔ ( ¬B ⇒ ¬A )'
        ],
      currentTask: ''
    }
  },
  emits: ['update-task'],
  components: {
    task: task
  },
  methods: {
    toUp(e) {
      this.currentTask = e.target.textContent
      this.$emit('up', {
        value: this.currentTask
      })
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.task_list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  row-gap: 30px;
  align-items: center;
}
</style>