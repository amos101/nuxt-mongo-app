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
  // const today = new Date();
  // let year = today.getFullYear();
  // let month = today.getMonth();
  const year = 2020
  const month = 4
export default ({
  mounted() {
    this.createCalendar()


  },
  methods: {
    //head
    getCalendarHead(){
      console.log("startgetCalendarHead1")
      const dates = []
      const d = new Date(year, month, 0).getDate()
      const n = new Date(year, month, 1).getDay()
      console.log("startgetCalendarHead2")
      for (let i = 0; i < n; ++i) {
        dates.unshift({
          date: d - i,
          isToday: false,
          isDisabled: true,
        })
      }
      return dates
    },
    //body
    getCalendarBody(){
      console.log("startgetCalendarbody1")
      const dates = []
      const lastDate = new Date(year, month + 1, 0).getDate()
      for (let i = 1; i <= lastDate; i++) {
        dates.push({
          date: i,
          isToday: false,
          isDisabled: false,
        })
      }
      console.log("finishgetCalendarbody2")
      return dates
    },
    //tail
    getCalendarTail(){
      console.log("startgetCalendartail1")
      const dates = []
      const lastDay = new Date(year, month + 1, 0).getDay()

      for (let i = 1; i < 7 - lastDay; i++) {
        dates.push({
          date: i,
          isToday: false,
          isDisabled: true,
        })
      }
      console.log(dates,2)
      return dates
    },
    createCalendar(){
      const dates = [
        ...this.getCalendarHead(),
        ...this.getCalendarBody(),
        ...this.getCalendarTail(),
      ]
      // const weeks = []
      // const weeksCount = dates.length / 7

      // for (let i = 0; i < weeksCount; i++) {
      //   weeks.push(dates.splice(0, 7))
      // }

      console.log(dates, 1)
    },
  }
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