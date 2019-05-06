<template>
  <v-flex xs12 sm6 lg4>
    <v-card class="course course__stream-fs">
      <v-img :src="course.fieldHeroImage.url">
      </v-img>

      <div class="v-card-content">
        <v-card-title>
          <div>
            <div class="course__type">Course type here</div>
            <div class="headline course__type-title">{{course.fieldCourseTitle}}</div>
          </div>
        </v-card-title>

        <v-card-actions>
          <v-flex xs12 sm6>
            <div class="course__info-title">COURSE LENGTH</div>
            <span class="course__info-length">{{stripWords(course.fieldCourseTimeCommitment, 2)}}</span>
          </v-flex>
          <v-flex xs12 sm6>
            <div class="course__info-title">NEXT START</div>
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
        font-weight: 500;
        font-size: 12px;
        color: #888888;
        text-transform: uppercase;
        &-title {
          font-weight: 500;
          font-size: 16px;
          color: #121212;
        }
      }
      &__info {
        &-title {
          color: #888888;
          font-size: 12px;
          padding-bottom: 4px;
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
