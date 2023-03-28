<template>
  <v-carousel 
  hide-delimiter-background
  cycle
  light
  >
    <v-carousel-item
     v-for="item in mainView" :key="item.title"
      reverse-transition
      >
      <v-row>
          <v-col>
            <my-main-view :main-img="item.img" :title="item.title" :subtitle="item.subtitle"></my-main-view>
          </v-col>
       </v-row>
     </v-carousel-item>
  </v-carousel>
</template>

<script>
import MyMainView from '~/components/MyMainView.vue'
export default {
  components: { MyMainView },
  data() {
    return {
      mainView: null,
    }
  },

  mounted() {
    this.$axios.get('https://4a1c8f74-cb5d-4daf-a857-45f1123af394.mock.pstmn.io/main').then((response) => {
      this.$data.mainView = response.data.data
    })
  },
}
</script>