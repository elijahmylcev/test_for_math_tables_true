<template>
  <button class="task">
    {{ task }}
  </button>
</template>

<script>
export default {
  name: 'task',
  props: {
    task: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>