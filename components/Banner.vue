<template>
  <v-jumbotron>
    <Ribbon />
    <v-container fill-height>
      <v-layout align-center>
        <v-flex text-xs-center>
          <h3 class="display-3">Courses</h3>
          <p>What do you want to learn?</p>
        </v-flex>
      </v-layout>
    </v-container>
  </v-jumbotron>
</template>

<script>
  import Ribbon from '~/components/Ribbon.vue'
  export default {
    components: {
      Ribbon
    }
  }
</script>

<style lang="scss">
.v-jumbotron {
  max-height: 264px;
  background-color: #f5f5f5;
}
</style>
