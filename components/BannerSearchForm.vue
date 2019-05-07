<template>
  <v-layout row wrap class="banner-search" >
    <v-flex xs12>
      <v-form v-model="valid" ref="form" class="banner-search__form">
        <v-layout row wrap>
          <v-flex xs11 sm9>
            <v-text-field
              v-model="search"
              placeholder="What do you want to learn?"
            ></v-text-field>
          </v-flex>
          <v-flex xs1 sm3>
            <v-btn round block depressed class="banner-search__button hidden-xs-only">Search</v-btn>
            <v-btn fab depressed class="banner-search__button xs hidden-sm-and-up">
              <v-icon>search</v-icon>
            </v-btn>
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
        .v-messages {
          display: none;
        }
        .v-input {
          padding: 0;
          margin: 0;
          &__slot{
            margin: 0;
            &:before,
            &:after {
              display: none;
            }
          }
          input {
            color: #000000;
            font-size: 18px;
            max-height: 45px;
            line-height: 45px;
            padding: 8px 17px;
            font-weight: 500;
            &::placeholder {
              color: #000000;
            }
          }
        }
        .v-btn {
          color: #ffffff;
          &.banner-search__button {
            height: 45px;
            margin: 0;
            background-color: #000054;
            border: 4px solid #ffffff;
            font-size: 16px;
            text-transform: none;
            &.xs {
              width: 45px;
            }
          }
        }
      }
      &__tagline {
        color: #7f7f7f;
        font-size: 13px;
        line-height: 24px;
        display: block;
        padding: 0 17px;
      }
    }
  }
</style>
