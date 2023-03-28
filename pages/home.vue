<template>
  <div>
    <my-item-tab :active-tab="1"></my-item-tab>
    <my-gender-btn  class="mt-4"></my-gender-btn>
    <my-carousel class="mt-8"></my-carousel>
    <div class="grey lighten-3 mt-6">
      <v-container>
        <v-row no-gutters >
          <v-col 
          md="3"><my-side-menu  class="grey lighten-3 mt-6"></my-side-menu></v-col>
          <v-col
          md="9"
          >
            <my-slider class="grey lighten-3 ml-10" ></my-slider>

        </v-col>
        </v-row>
     
      </v-container>
    </div>
  </div>
</template>

<script>

</script>