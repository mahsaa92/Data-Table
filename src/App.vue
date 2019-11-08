<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <h2 id="header">Vue Data Table</h2>
    </v-app-bar>
    <v-content>
      <DataTable />
    </v-content>
  </v-app>
</template>

<script>
import DataTable from "./components/DataTable";

export default {
  name: "App",

  components: {
    DataTable
  },

  data: () => ({
    //
  })
};
</script>
