<template>
  <v-card
    flat
  >
    <v-window
      v-model="onboarding"
      :continuous="true"
      show-arrows
    >

    <template #:prev="{ on, attrs }">
      <v-btn
        depressed
        height="64px"
        class="rounded-circle p-0"
        color="rgba(66, 66, 66,0.2)"
        v-bind="attrs"
        v-on="on"
      ><v-icon
      class="white--text"
      >mdi-chevron-left</v-icon></v-btn>
    </template>
    
    <template #next="{ on, attrs }">
      <v-btn
      depressed
        height="64px"
        class="rounded-circle p-0"
        color="rgba(66, 66, 66,0.2)"
        v-bind="attrs"
        v-on="on"
      ><v-icon
      class="white--text"
      >mdi-chevron-right</v-icon></v-btn>
    </template>
      <v-window-item
        v-for="n in length"
        :key="`card-${n}`"
      >
        <v-card
          color="grey"
          height="200"
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
          >

         
            <h1
              style="font-size: 5rem;"
              class="white--text"
            >
              Slide {{ n }}
            </h1>

        
          </v-row>
        </v-card>
      </v-window-item>
    </v-window>

    <v-card-actions class="justify-center">
      
      <v-item-group
        v-model="onboarding"
        class="text-center"
        mandatory
      >
        <v-item
          v-for="n in length"
          :key="`btn-${n}`"
          v-slot="{ active, toggle }"
        >
          <v-btn
            :input-value="active"
            icon
            @click="toggle"
          >
            <v-icon>mdi-record</v-icon>
          </v-btn>
        </v-item>
      </v-item-group>
      
    </v-card-actions>
  </v-card>
</template>
<script>
  export default {
    data: () => ({
      length: 3,
      onboarding: 0,
    }),

    methods: {
      next () {
        this.onboarding = this.onboarding + 1 === this.length
          ? 0
          : this.onboarding + 1
      },
      prev () {
        this.onboarding = this.onboarding - 1 < 0
          ? this.length - 1
          : this.onboarding - 1
      },
    },
  }
</script>