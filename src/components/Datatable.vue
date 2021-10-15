<template>
  <div>
    <table class="data-table">
      <thead>
        <tr>
          <th v-for="(i, id) in headers" :key="id">{{ i }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(i, id) in items" :key="id">
          <td>{{ i.name }}</td>
          <td>{{ i.calories }}</td>
          <td>{{ i.fat }}</td>
          <td>{{ i.protein }}</td>
          <td>{{ i.carbohydrates }}</td>
          <td>{{ i.iron }}</td>
        </tr>
      </tbody>
      <tr>
        <slot name="bodyappend" />
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    headers: {
      type: Array
    },
    items: {
      type: Array
    }
  }
};
</script>

<style scoped>
.data-table {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  margin: 40px;
  border-collapse: collapse;
  font-size: 0.9em;
  font-family: sans-serif;
  min-width: 400px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.data-table td,
th {
  text-align: left;
}
.data-table footer {
  margin: 30px 0 30px 0;
  font-style: italic;
}
.data-table thead tr {
  background-color: #009879;
  color: #ffffff;
  text-align: left;
}
.data-table th,
.data-table td {
  padding: 12px 15px;
}
.data-table tbody tr {
  border-bottom: 1px solid #dddddd;
}
.data-table tbody tr:nth-of-type(even) {
  background-color: #f3f3f3;
}
</style>
