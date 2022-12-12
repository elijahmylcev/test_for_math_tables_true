<template>
  <div class="solution">
    <div v-if="currentTask == ''">
      <h2 class="solution__title">Выберите задание</h2>
      <div class="circle">
        <div class="circle-u"></div>
      </div>

    </div>
    <div v-else class="questions">
      <h2>{{ currentTask }}</h2>

      <div id="count_strings" class="question_item">
        <label for="strings">Сколько строк должно быть в таблице истинности?</label>
        <input @change="(e) => updateRow(e)" type="text" id="strings" placeholder="Кол-во срок" />
      </div>

      <div id="count_columns" class="question_item">
        <label for="columns">Сколько колонок должно быть в таблице истинности?</label>
        <input @change="(e) => updateColumns(e)" type="text" id="columns" placeholder="Кол-во колонок" />
      </div>

      <div id="table">
        Заполните таблицу истинности
        <Table :columns="this.columns" :row="this.row" />
      </div>
    </div>
  </div>
</template>

<script lang="js">
import table from './table.vue'
export default {
  name: 'Solution',
  data() {
    return {
      row: [],
      columns: []
    }
  },
  props: {
    currentTask: String
  },
  components: {
    Table: table
  },
  methods: {
    updateColumns(n) {
      this.columns = []
      let count = Number(n.target.value)
      while (count > 0) {
        this.columns.push(count)
        count--
      }
    },

    updateRow(n) {
      this.row = []
      let count = Number(n.target.value)
      while (count > 0) {
        this.row.push(count)
        count--
      }

      console.log(this.row);
    }
  },
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
  box-shadow: 1px 1px 15px rgba(143, 161, 4, 0.6);
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

.questions {
  display: flex;
  flex-direction: column;
  row-gap: 25px;
  justify-content: flex-start;
  align-items: center
}

.question_item {
  display: flex;
  flex-direction: column;
  gap: 10px
}

input {
  padding: 15px 20px;
  border: 1px solid black;
  border-radius: 10px;
}

Table {
  margin-top: 20px;
}
</style>