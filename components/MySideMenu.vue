<template>
  <v-card
    class="mx-auto"
    max-width="400"
    tile
    flat
  >
    <v-list
      nav
      dense
      class="grey lighten-3"
    >
      <v-list-item-title class="text-h6">Search</v-list-item-title>
      <v-list-item-group
      flat>
        <v-list-item 
        v-for="item in list" :key="item.condition"
        flat> 
          <v-list-item-content>
          <v-list-item-subtitle class="text-body-2">{{ item.condition }}</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
    <v-divider></v-divider>
    <div class="mt-5 text-h6">Search by Category</div>
    <v-row
    v-for="button in category"
    :key="button.title"
    class="ma-4"
    >
        <my-offset-btn-x :title="button.title"></my-offset-btn-x>
    </v-row>

    <v-divider></v-divider>
    <div class="mt-5 text-h6">Favorite</div>
    <v-row
    v-for="favItem in fav"
    :key="favItem.favorite"
    class="ma-4"
    >
        <my-offset-btn-x :title="favItem.favorite"></my-offset-btn-x>
    </v-row>
  </v-card>
</template>
<script>
export default{
  data: () =>({
  list: [
  {
    condition:'Search by brand'
  },{
    condition: 'Search from the official shop'
  },{
    condition: 'Search by ranking'
  },{
    condition: 'Search by sale'
  },{
    condition: 'Search by coupon target'
  },{
    condition: 'Search by coordinates'
  },{
    condition: 'Search by special conditions'
  },{
    condition: 'Search by used clothes'
  }
  ],
  category : [
  {title:'tops'},
  {title:'jacket/outer'},
  {title:'pants'},
  {title:'all in one'},
  {title:'skirt'},
  {title:'dress/dress'},
  {title:'Formal suits/accessories'},
  {title:'bag'},
  {title:'shoes'},
  {title:'Clothes miscellaneous goods'},
  {title:'Purses/Accessories'},
  {title:'watch'},
  {title:'hair accessory'},
  {title:'accessories'},
  {title:'underwear'},
  {title:'leg wear'},
  {title:'down wear'},
  {title:'hat'},
  {title:'interior'},
  {title:'tableware/kitchen'},
  {title:'Miscellaneous Goods/Hobbies'},
  {title:'PC/Smartphone Goods/Home Appliances'},
  {title:'skin care'},
  {title:'base makeup'},
  {title:'Makeup'},
  {title:'beauty goods'},
  {title:'body and hair care'},
  {title:'fragrance'},
  {title:'Swimwear/Kimono/Bath'}
  ],

  fav : [
  {favorite:'item'},
  {favorite:'brand'},
  {favorite:'shop'}   
  ],

})
}



</script>