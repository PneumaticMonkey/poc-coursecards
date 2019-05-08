<template>
  <v-flex xs12 sm6 lg4>
    <v-card :class="stream(course.stream)" class="course fill-height">
      <v-img :src="course.fieldHeroImage.url">
      </v-img>
      <v-card-text class="grow">
        <v-fab-transition>
          <v-btn
            v-show="!hidden"
            fab
            depressed
            flat
            small
            absolute
            right
            @click="hidden = !hidden"
            class="course__btn-favourite"
          >
            <v-icon>favorite_border</v-icon>
          </v-btn>
        </v-fab-transition>
        <v-fab-transition>
          <v-btn
            v-show="hidden"
            fab
            depressed
            flat
            small
            absolute
            right
            @click="hidden = !hidden"
            class="course__btn-favourite"
          >
            <v-icon>favorite</v-icon>
          </v-btn>
        </v-fab-transition>
        <span class="course__type">{{course.stream}}</span>
        <span class="course__type-title">{{course.fieldCourseTitle}}</span>
        <span v-if="course.fieldCourseDetails" class="course__details">{{course.fieldCourseDetails}}</span>
      </v-card-text>
      <v-card-link>
        <v-btn v-if="course.entityUrl.path" flat small nuxt :href="course.entityUrl.path" class="course__link-details">View details</v-btn>
      </v-card-link>
      <v-card-actions>
        <v-flex xs12 sm6>
          <span class="course__info-title">DURATION</span>
          <span class="course__info-length">{{stripWords(course.fieldCourseTimeCommitment)}}</span>
        </v-flex>
        <v-flex xs12 sm6>
          <span class="course__info-title">NEXT INTAKE</span>
          <span class="course__info-start">{{course.fieldCourseStartDateV2.date | moment("DD MMM YYYY")}}</span>
        </v-flex>
      </v-card-actions>
    </v-card>
  </v-flex>
</template>

<script>
  import Vue from 'vue'
  import moment from 'vue-moment'

  Vue.use(moment)

  export default {
    data: () => ({
      hidden: false
    }),
    props: ['course'],
    methods: {
      stripWords(string) {
        return string.replace(/ \([\s\S]*?\)/g, '');
      },
      stream(stream) {
        var s = "course__stream-"
        if (stream.toLowerCase() == "future skills short course") {
          s = s + "fs";
        }
        else if (stream.toLowerCase() == "postgraduate") {
          s = s + "pg";
        }
        else if (stream.toLowerCase() == "undergraduate") {
          s = s + "ug";
        }
        else {
          s = "";
        }
        return s;
      }
    }
  }
</script>

<style lang="scss">
.card-grid {
  @media (max-width: $se-max) {
    padding: 0;
  }
}
.v-card {
  display: flex;
  flex-direction: column;
  &.v-sheet {
    border-radius: 5px;
    @media (max-width: $se-max) {
      border-radius: 0;
    }
  }
  &.course {
    .v-image {
      max-height: 174px;
      overflow: hidden;
      border-bottom: 8px solid $mid-grey;
    }
    &__stream {
      &-fs {
        .v-image {
          border-color: $bright-cyan;
        }
      }
      &-pg {
        .v-image {
          border-color: $red;
        }
      }
      &-ug {
        .v-image {
          border-color: $marigold;
        }
      }
    }
    .course {
      &__type {
        display: block;
        width: 100%;
        font-weight: 500;
        font-size: 12px;
        color: $black-18-05;
        text-transform: uppercase;
        padding-right: 50px;
        padding-bottom: 5px;
        &-title {
          display: block;
          width: 100%;
          font-weight: 500;
          font-size: 16px;
          line-height: 22px;
          color: $dark-grey;
          padding-right: 50px;
        }
      }
      &__link-details {
        .v-btn__content {
          color: $blue;
        }
      }
      &__info {
        &-title {
          display: block;
          color: $black-18-05;
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
      &__details {
        display: block;
        padding: 16px 0;
      }
    }
  }
  &__text {
    position: relative;
    .course {
      &__btn {
        &-favourite {
          top: 16px;
          color: $orangish;
          .v-icon {
            font-size: 20px;
          }
        }
      }
    }
  }
  &__title {
    padding: 0 0 16px;
  }
  &__actions {
    border-top: 1px solid $mid-grey;
    padding: 16px 0 17px;
    margin: 0 17px;
    .course & {
      .container & {
        .flex {
          padding: 0;
        }
      }
    }
  }
}
</style>
