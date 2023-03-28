<template>
  <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="300"
    flat
  >
    <v-img
      height="200"
      :src="clothImg"
    ></v-img>
    <div class="pa-4 text-subtitle-2">{{clothName}}</div>
    <v-card-text>
      <!-- This align about align item -->
      <v-row
        align="center"
        class="mx-0"
      >
      </v-row> 
      <div class="my-4 text-subtitle-1">
        T-shirt / Cuttsor 
      </div>
      <p 
      class="black--text text-h5 font-weight-bold mt-4"
      >{{ price }}</p>
      <div class="my-2">
        Total 6 colors
      </div>
    </v-card-text>

    
  </v-card>
</template>
<script>
  export default {
    props: {
      clothImg: {
        type: String,
        default: '',
      },
      clothName: {
        type: String,
        default: '',
      },
      price: {
        type: String,
        default: '',
      },
    },
    data: () => ({
      loading: false,
      selection: 1,
    })
  }
</script>
