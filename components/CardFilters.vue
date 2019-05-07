<template>
  <v-container class="course-filters">
    <v-flex>
      <v-btn depressed outline input-value="true">All (30)</v-btn>
      <v-btn depressed outline><span class="course--stream-block fs"></span> Future Skills short course (23)</v-btn>
      <v-btn depressed outline><span class="course--stream-block ug"></span> Undergraduate (12)</v-btn>
      <v-btn depressed outline><span class="course--stream-block pg"></span> Postgraduate (12)</v-btn>
    </v-flex>
  </v-container>
</template>

<script>
  export default {

  }
</script>

<style lang="scss">
  .container {
    &.course-filters {
      .v-btn {
        font-size: 12px;
        @media (min-width: $lg-min) {
          font-size: 16px;
        }
        &--active {
          background-color: $greyish-brown-1 !important;
          color: $white;
        }
        .course--stream-block {
          display: block;
          height: 15px;
          width: 15px;
          background: $light-grey;
          margin-right: 10px;
          border-radius: 2px;
          &.fs {
            background: $bright-cyan;
          }
          &.ug {
            background: $marigold;
          }
          &.pg {
            background: $red;
          }
        }
      }
    }
  }
</style>
