<template>
  <div class="grey lighten-3">
    <v-container>
    <v-row align="center"  justify="space-between">
      <v-col 
      :style="getStyle(1)" 
      class="text-h6 text-center " 
      @click="onClick(1)">
          All Item
      </v-col>
      <v-col 
      :style="getStyle(2)" 
      class="text-center text-h6 " 
      @click="onClick(2)">
        Shoes Item
      </v-col>
      <v-col 
      :style="getStyle(3)" 
      class="text-h6 text-center " 
      @click="onClick(3)">
          Cosmetic Item
      </v-col>
    </v-row>
  </v-container>
  </div>
</template>
<script>
export default {
  props: {
    activeTab: {
      type: Number,
      default: 1,
    },
  },
  methods: {
    getStyle(item) {
      return item === this.$props.activeTab ? 'border-bottom:solid black 2px' : 'cursor: pointer'
    },
    onClick(item) {
      switch (item) {
        case 1:
          // goto page 1
          this.$router.push('/home')
          break
        case 2:
          this.$router.push('/inspire')
          // goto page 2
          break
        case 3:
          this.$router.push('/clothes')
          break
        // goto page 3
      }
    },
  },
}
</script>