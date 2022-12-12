<template>
  <div class="general">
    <h1 class="dsongentom desetungavon">Проверьте, являются ли данные выражения абсолютной истиной</h1>
    <task_list @up="increase" />
    <Solution :currentTask="currentTask" class="solution" />
  </div>
</template>

<script>
import tasks_list from './tasks_list.vue';
import Solution from './Solution.vue'
export default {
  name: 'general',
  data() {
    return {
      currentTask: ''
    }
  },
  components: {
    task_list: tasks_list,
    Solution
  },
  props: {
    tasks: Array
  },
  methods: {
    increase(n) {
      this.currentTask = n.value
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dsongentom {
  position: relative;
  top: 50%;
  width: 35em;
  margin: 0 auto;
  border-right: 2px solid rgba(255, 255, 255, .75);
  font-size: 180%;
  text-align: center;
  white-space: nowrap;
  overflow: hidden;
  transform: translateY(-50%);
}

h1:after {
  content: '';
  display: block;
  width: 15px;
  height: 30px;
  background-color: rgba(30, 30, 209, .6);
  position: absolute;
  top: 0;
  right: 0;
  animation: lol 500ms steps(44) step-end infinite;
}

@keyframes lol {
  from {
    display: 0;
  }

  to {
    opacity: 1;
  }
}

.desetungavon {
  animation: typewriter 4s steps(44) 1s 1 normal both,
    blinkTextCursor 500ms steps(44) infinite normal;
}

@keyframes typewriter {
  from {
    width: 0;
  }

  to {
    width: 35em;
  }
}

.solution {
  margin-top: 20px;
}
</style>
