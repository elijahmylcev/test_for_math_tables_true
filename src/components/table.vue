<template>
  <table>
    <!-- <thead>
      <tr>
        <th v-for="n in headers"></th>
      </tr>
    </thead> -->
    <tbody>
      <tr v-for="item in row" :key="item">
        <!-- <input type="text"> -->
        <td v-for="n in columns" :key="n">
          <input type="text">
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'table',
  props: ['row', 'columns']
}
</script>

<style scoped>
table {
  /* table-layout: fixed; */
  width: 100%;
  height: 100%;
  border-collapse: collapse;
  border: 1px solid black;
  margin-bottom: 30px;
  /* border-spacing: 3px; */
}


tr,
th,
td {
  padding: 20px;
  border: solid 2px black;
}

tr {
  width: fit-content;
}

input {
  width: fit-content;
  font-size: 20px;
  /* width: 50%; */
  border: none;
  outline: none;
  padding: 5px;
  text-align: center;
}
</style>