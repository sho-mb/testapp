<template>
  <div>
   <my-item-tab :active-tab="3"></my-item-tab>

    <v-row  v-for="item in clothes" :key="item.name">
      <v-col>
        <my-card :cloth-img="item.img" :cloth-name="item.name" :price="item.price + ' $'"></my-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import MyCard from '~/components/MyCard.vue'
export default {
  components: { MyCard },
  data() {
    return {
      clothes: null,
    }
  },

  mounted() {
    this.$axios.get('https://9e573f4d-70bc-48ad-84af-1436ffc7d9d3.mock.pstmn.io/clothes').then((response) => {
      this.$data.clothes = response.data.data
    })
  },
}
</script>
