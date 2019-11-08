<template>
  <v-container>
 <div>
    <v-data-table
      :headers="headers"
      :items="user_data"
      item-key="name"
      class="elevation-1"
      :search="search"
      dark
    >
      <template v-slot:top>
        <v-text-field v-model="search" label="Search" class="mx-4"></v-text-field>
      </template>
    <template slot="user_data">
    </template>
    </v-data-table>
  </div>
  </v-container>
</template>

<script>
import axios from 'axios'
export default {
  name: 'DataTable',

    data () {
      return {
        search: '',
        user_data : []
      }
    },
    computed: {
      headers () {
        return [
          {
            text: 'id',
            align: 'left',
            sortable: true,
            value: 'id',
          },
          {
            text: 'name',
            align: 'left',
            sortable: true,
            value: 'name',
          },
          {
            text: 'username',
            align: 'left',
            sortable: true,
            value: 'username',
            },
                                  {
            text: 'email',
            align: 'left',
            sortable: true,
            value: 'email',
            },
          {
            text: 'phone',
            align: 'left',
            sortable: true,
            value: 'phone',
            },
        ]
      },
    },
    methods: {},
    mounted() {
        axios
          .get('https://jsonplaceholder.typicode.com/users')
          .then(response => (this.user_data = response.data))
          .catch(error=> alert(error))
    }
  }
</script>

