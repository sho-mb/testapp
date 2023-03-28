<template>
  <v-table>
    <thead>
      <tr>
        <th class="text-left">Id</th>
        <th class="text-left">Name</th>
        <th class="text-left">Sex</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in rows" :key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>{{ item.sex }}</td>
      </tr>
    </tbody>
  </v-table>
</template>
<script lang="ts">
export interface User {
  id: string
  name: string
  sex: string
}

export default {
  props: {
    rows: {
      type: Array as () => User[],
      default: Array,
    },
  },
}
</script>
