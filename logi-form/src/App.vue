<template>
<div id="app" class="small-container">
    <h1>Employees</h1>
    <employee-form @add:employee="addEmployee"/>
    <employee-table v-bind:employees="employees" />
</div>
</template>

<script>
import EmployeeForm from '@/components/EmployeeForm.vue'
import employeeTable from '@/components/employeeTable.vue'

export default {
    name: 'app',
    components: {
        EmployeeForm,
        employeeTable
    },
    data() {
        return {
            employees: [{
                    id: 1,
                    name: 'John Patrick',
                    email: 'john@gmail.com',
                },
                {
                    id: 2,
                    name: 'Patrick',
                    email: 'pat@gmail.com'
                }
            ]
        }
    },
    methods:{
      addEmployee(employee){
        const lastId=
          this.employees.length>0
            ? this.employees[this.employees.length-1].id
            :0;
        const id = lastId-1;
        const newEmployee={...employee, id};

        this.employees = [...this.employees, newEmployee]
      }
    }
}
</script>

<style>
button {
    background: #009435;
    border: 1px solid #009435;
}

.small-container {
    max-width: 680px;
}
</style>
