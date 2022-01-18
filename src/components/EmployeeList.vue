<template>
  <div class="list">
    <h1>EMPLOYEE LIST</h1>
    <div>
      <table>
        <tr>
          <th>ID</th>
          <th>NAME</th>
          <th>AGE</th>
          <th>SALARY</th>
        </tr>
        <tr v-for="item in list" v-bind:key="item">
          <td>{{item.id}}</td>
          <td>{{item.employee_name}}</td>
          <td>{{item.employee_age}}</td>
          <td>${{item.employee_salary}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  name: 'EmployeeList',
  data() {
    return {
      list: undefined,
    }
  },
  mounted () {
    Vue.axios.get('http://dummy.restapiexample.com/api/v1/employees')
    .then((response)=>{
      this.list = response.data.data;
      console.warn(response.data.data)
    })
  }
}
</script>

<style scoped>
h1 {
  width: 40%;
  margin: 0 auto;
  margin-top: 30px;
  padding-bottom: 20px;
  font-size: 46px;
  text-align: center;
  color: #333;
  border-bottom: 3px solid #333;
}
table {
  margin: 0 auto;
  margin-top: 35px;
  margin-bottom: 35px;
  border-collapse: collapse;
}
td, th {
  border: 2px solid #333;
  padding: 10px;
}
th:nth-child(1), td:nth-child(1), th:nth-child(3), td:nth-child(3) {
  width: 25px;
  text-align: center;
}
th:nth-child(2), td:nth-child(2) {
  width: 250px;
  text-align: left;
}
th:nth-child(4), td:nth-child(4)  {
  width: 120px;
  text-align: center;
}
tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
