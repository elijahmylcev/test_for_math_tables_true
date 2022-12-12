<template>
  <div class="general">
    <h1>Проверьте, являются ли данные выражения абсолютной истиной</h1>
    <task_list />
  </div>
</template>

<script>
import tasks_list from './tasks_list.vue';
export default {
  name: 'general',
  components: {
    task_list: tasks_list
  },
  props: {
    tasks: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
