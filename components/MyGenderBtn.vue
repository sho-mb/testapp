<template>
  <div>
    <v-container>
      <v-btn
      depressed
      text
      :ripple="false"
      :style="active(1)"
      @click="onClick(1)"
      >All</v-btn>
      <v-btn
      color="primary"
      depressed
      text
      :ripple="false"
      :style="active(2)"
      @click="onClick(2)"
      >
        <v-icon left>
          mdi-human-male
        </v-icon>
        Male
      </v-btn>
      <v-btn
      color="pink"
      depressed
      text
      :ripple="false"
      :style="active(3)"
      @click="onClick(3)"
      >
      <v-icon left>
          mdi-human-female
        </v-icon>
        Female
      </v-btn>
      <v-btn
      color="yellow accent-4"
      depressed
      text
      :ripple="false"
      :style="active(4)"
      @click="onClick(4)"
      >
      <v-icon left>
          mdi-human-child
        </v-icon>
        Kids
      </v-btn>
    </v-container>
  </div>
</template>
<script>
export default{
  props: {
    activeBtn: {
      type: Number,
      default: 1,
    }
  },
  methods: {
    active(item){
      return this.$props.activeBtn === item ? 'background-color:#EEEEEE' : ''
    },
    onClick(item){
      switch (item) {
        case 1:
          this.$props.activeBtn = item
          break
        case 2:
          this.$props.activeBtn = item
          break
        case 3:
          this.$props.activeBtn = item
          break
        case 4:
        this.$props.activeBtn = item
        break
        // goto page 3
      }
    }
  }
}
</script>