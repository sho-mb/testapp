<template>
  <v-sheet
    max-width="100%"
  >
  <div class="text-h4 ml-12 mt-8">Popular Item</div>
    <v-slide-group
      show-arrows
    >
        <v-slide-item
          v-for="item in clothes"
          :key="item.name"
        >
          <my-card :cloth-img="item.img" :cloth-name="item.name" :price="item.price + ' $'"></my-card>
        </v-slide-item>
    </v-slide-group>

    <div class="text-h4 ml-12 mt-8">Discount Item</div>
    <v-slide-group
      show-arrows
    >
        <v-slide-items
          v-for="item in discountClothes"
          :key="item.name">
          <my-card :cloth-img="item.img" :cloth-name="item.name" :price="item.price + ' $'"></my-card>
        </v-slide-items>
    </v-slide-group>
     
  </v-sheet>
</template>
<style>
  .v-slide-group__content {
    height: 480px;
    align-items: self-end;
  }
</style>
<script>
import MyCard from '~/components/MyCard.vue'
export default {
  props: {
    category: {
      type: String,
      default: "",
    },
  },
  data(){
    return a = this.$props.category
  },
  components: { MyCard },
  data() {
    return {
      clothes: null,
      discountClothes: null,
    }
  },

  mounted() {
    this.$axios.get('https://9e573f4d-70bc-48ad-84af-1436ffc7d9d3.mock.pstmn.io/clothes').then((response) => {
      this.$data.clothes = response.data.data
    }),

    this.$axios.get('https://1a4980cb-cad2-4b38-bd40-7e93b4e10a10.mock.pstmn.io/discountClothes').then((response) => {
      this.$data.discountClothes = response.data.data
    })
  },
}
</script>