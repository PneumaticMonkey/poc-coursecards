<template>
  <v-layout row wrap class="banner-search" >
    <v-flex xs12>
      <v-form v-model="valid" ref="form" class="banner-search__form">
        <v-layout row wrap>
          <v-flex xs10>
            <v-text-field
              v-model="search"
              label="What do you want to learn?"
              required
            ></v-text-field>
          </v-flex>
          <v-flex xs2>
            <v-btn large round block depressed class="banner-search__button">Search</v-btn>
          </v-flex>
        </v-layout>
      </v-form>
      <span class="banner-search__tagline">Search for courses, programs and keywords</span>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {

  }
</script>

<style lang="scss">
  .banner {
    .banner-search {
      &__form {
        background: #ffffff;
        border-radius: 28px;
        .v-btn {
          color: #ffffff;
          &.banner-search__button {
            margin: 0;
            background-color: #000054;
            border: 4px solid #ffffff;
          }
        }
      }
    }
  }
</style>
