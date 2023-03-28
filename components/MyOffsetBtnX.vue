<template>
  <div>
    <v-menu
      :offset-x="true"
    >
      <template 
      v-slot:activator="{ on, attrs }"
      >
      <v-row justify="start">
        <v-btn
          text
          class="mt-3"
          v-bind="attrs"
          v-on="on"
        >
          {{ title }}
        </v-btn>
      </v-row>
      </template>

      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>
<script>
  export default {
    props: {
    title: {
      type: String,
      default:"",
    },
    
  },
    data: () => ({
      offset: true,
      items: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],
    }),
  }
</script>