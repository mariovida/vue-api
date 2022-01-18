<template>
  <div id="app">
    <EmployeeList />
  </div>
</template>

<script>
import EmployeeList from './components/EmployeeList.vue'

export default {
  name: 'App',
  components: {
    EmployeeList
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@100;200;300;400;500;600;700;800;900&display=swap');
* {
  margin: 0;
  padding: 0;
  font-family: 'Montserrat';
}
</style>
