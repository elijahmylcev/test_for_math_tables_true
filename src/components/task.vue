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
.task {
  min-width: 350px;
  border: 1px solid grey;
  padding: 10px 18px;
  background-color: transparent;
  font-size: 28px;
  cursor: pointer;
  transition: all .4s;
}

.task:hover {
  box-shadow: 1px 1px 15px rgba(30, 30, 209, .6);
  text-shadow: 1px 1px 4px rgba(30, 30, 209, .6);
}
</style>