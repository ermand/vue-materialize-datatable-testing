<template>
  <div class="hello">
    <h1>Users</h1>
    <p v-if="selectedEmail">Selected email: {{ selectedEmail }}</p>

    <div class="w-full">
      <datatable :columns="columns" :rows="data" v-on:row-click="onRowClick"></datatable>
    </div>
  </div>
</template>

<script>
import DataTable from 'vue-materialize-datatable';

export default {
  name: 'UsersList',
  components: {
    datatable: DataTable
  },
  data() {
    return {
      selectedEmail: null,
      title: 'Users list',
      columns: [
        {
          label: 'Name',
          field: 'name',
          numeric: false,
        },
        {
          label: 'Email',
          field: 'email',
          numeric: false,
        },
      ],
      data: [
        {
          name: 'Ermand Durro',
          email: 'ermand.durro@example.com',
        },
        {
          name: 'Admin User',
          email: 'admin@example.com',
        },
      ]
    }
  },
  methods: {
    onRowClick(row) {
      this.selectedEmail = row.email;
    }
  }
}
</script>

<style scoped>
@import url('http://fonts.googleapis.com/icon?family=Material+Icons');
.w-full {
  width: 100%;
}
table {
  width: 100%;
}
</style>
