<template>
    <v-card
    :loading="loading"
    class="mx-auto"
    max-width="80%"
   >
    <v-img
    :src="mainImg"
    height="400px"
    class="white--text align-end">
    <v-card-title>{{ title }}</v-card-title>
    <v-card-subtitle>{{ subtitle }}</v-card-subtitle>
    </v-img>
  </v-card>
</template>
<script>
   export default {
    props: {
      mainImg: {
        type: String,
        default: '',
      },
      title: {
        type: String,
        default: '',
      },
      subtitle: {
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
<!-- <style>
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
</style> -->