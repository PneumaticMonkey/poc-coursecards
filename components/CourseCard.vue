<template>
  <v-flex xs12 sm6 lg4>
    <v-card class="course course__stream-fs">
      <v-img :src="course.fieldHeroImage.url">
      </v-img>

      <div class="v-card-content">
        <v-card-title>
          <span class="course__type">Course type here</span>
          <span class="headline course__type-title">{{course.fieldCourseTitle}}</span>
        </v-card-title>

        <v-card-actions>
          <v-flex xs12 sm6>
            <span class="course__info-title">COURSE LENGTH</span>
            <span class="course__info-length">{{stripWords(course.fieldCourseTimeCommitment, 2)}}</span>
          </v-flex>
          <v-flex xs12 sm6>
            <span class="course__info-title">NEXT START</span>
            <span class="course__info-start">{{course.fieldCourseStartDateV2.date | moment("DD MMM YYYY")}}</span>
          </v-flex>
        </v-card-actions>
      </div>
    </v-card>
  </v-flex>
</template>

<script>
  import Vue from 'vue'
  import moment from 'vue-moment'

  Vue.use(moment)

  export default {
    props: ['course'],
    methods: {
      stripWords(string, spaceClip) {
        return string.split(" ").splice(0,spaceClip).join(" ");
      }
    }
  }
</script>

<style lang="scss">
.v-card {
  &.course {
    .v-image {
      max-height: 174px;
      overflow: hidden;
      border-bottom: 8px solid #e2e2e2;
    }
    &__stream {
      &-fs {
        .v-image {
          border-color: #50d2ff;
        }
      }
    }
    .course {
      &__type {
        display: block;
        font-weight: 500;
        font-size: 12px;
        color: #888888;
        text-transform: uppercase;
        &-title {
          display: block;
          font-weight: 500;
          font-size: 16px;
          color: #121212;
        }
      }
      &__info {
        &-title {
          display: block;
          color: #888888;
          font-size: 12px;
          padding-bottom: 4px;
        }
        &-length {
          display: block;
        }
        &-start {
          display: block;
        }
      }
    }
  }
  &-content {
    padding: 14px 17px 17px;
  }
  &__title {
    padding: 0 0 16px;
  }
  &__actions {
    border-top: 1px solid #e2e2e2;
    padding: 16px 0 0;
  }
}
</style>
