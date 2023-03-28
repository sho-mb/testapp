<template>
  <v-row>
    <v-col class="text-center">
      <my-item-tab :active-tab="2"></my-item-tab>
     
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;12John Johnsonffffff</em>
          </small>
        </footer>
      </blockquote>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'InspirePage',
}
</script>
