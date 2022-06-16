<template>
  <div>
    <table>
      <thead>
        <tr>
          <th id="prev">&laquo;</th>
          <th id="title" colspan="5">2020/05</th>
          <th id="next">&raquo;</th>
        </tr>
        <tr>
          <th>Sun</th>
          <th>Mon</th>
          <th>Tue</th>
          <th>Wed</th>
          <th>Thu</th>
          <th>Fri</th>
          <th>Sat</th>
        </tr>
      </thead>
      <tbody>
      </tbody>
      <tfoot>
        <tr>
          <td id="today" colspan="7">Today</td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>
<script>
  const today = new Date();
  let year = today.getFullYear();
  let month = today.getMonth();
export default ({
  })
</script>
<style scoped>
body {
  font-family: 'Courier New', monospace;
  font-size: 14px;
}

table {
  border-collapse: collapse;
  border: 2px solid #eee;
}

thead,
tfoot {
  background: #eee;
}

th,
td {
  padding: 8px;
  text-align: center;
}

tbody td:first-child {
  color: red;
}

tbody td:last-child {
  color: blue;
}

tfoot {
  font-weight: bold;
}

td.disabled {
  opacity: 0.3;
}

td.today {
  font-weight: bold;
}

#prev,
#next,
#today {
  cursor: pointer;
  user-select: none;
}
</style>