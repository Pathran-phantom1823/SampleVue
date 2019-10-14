<template>
<div id="employee-table">
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Email</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="employee in employees" v-bind:key="employee.id">
                <td>{{employee.name}}</td>
                <td>{{employee.email}} </td>

                <td>
                <button>Edit</button>
                <button>Delete</button>
                </td>   
            </tr>
        </tbody>
    </table>
</div>
</template>

<script>
export default {
    name: 'employee-table',
    props: {
        employees: Array,
    }
}
</script>

<style scoped>
</style>
