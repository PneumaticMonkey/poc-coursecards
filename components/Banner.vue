<template>
  <v-responsive class="banner">
    <Ribbon />
    <v-container fill-height>
      <v-layout align-center>
        <v-flex text-xs-center>
          <h2 class="display-3">Courses</h2>
          <v-flex xs12>
            <BannerSearchForm />
          </v-flex>
        </v-flex>
      </v-layout>
    </v-container>
  </v-responsive>
</template>

<script>
  import Ribbon from '~/components/Ribbon.vue'
  import BannerSearchForm from '~/components/BannerSearchForm.vue'
  export default {
    components: {
      Ribbon,
      BannerSearchForm
    }
  }
</script>

<style lang="scss">
.banner {
  position: relative;
  height: 100%;
  min-height: 264px;
  background-color: #f5f5f5;
}
</style>
