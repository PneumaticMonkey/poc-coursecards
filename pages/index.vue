<template>
  <section>
    <div class="container">
      <div class="row">
        <div class="col s12 center">
          <h1 class="title">Course cards POC</h1>
        </div>
      </div>

      <div class="row">
        <div v-for="course in data.nodeQuery.entities" v-if="course.fieldShowInCatalogue" class="col s12 m6 xl4">
          <div class="card medium course course-stream-fs">
            <div class="card-image">
              <img :src="course.fieldHeroImage.url" />
            </div>
            <div class="card-content">
              <div class="course-type">COURSE TYPE HERE</div>
              <div class="course-title">{{course.fieldCourseTitle}}</div>
            </div>
            <div class="card-action course-info">
              <div class="row">
                <div class="col s12 m6">
                  COURSE LENGTH
                  <br />
                  <span class="course-length">{{stripWords(course.fieldCourseTimeCommitment, 2)}}</span>
                </div>
                <div class="col s12 m6">
                  NEXT START
                  <br />
                  <span class="course-start">{{course.fieldCourseStartDateV2.date | moment("DD MMM YYYY")}}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Vue from 'vue';
import moment from 'vue-moment';

Vue.use(moment);

  export default {
    methods: {
      stripWords(string, spaceClip) {
        // return "LALALALALA" + string + ", " + spaceClip;
        return string.split(" ").splice(0,spaceClip).join(" ");
      }
    },
    async asyncData ({ app }) {
      const { data } = await app.$axios.$get('/courses.json');
      return {data};
    }
  }
</script>

<style>
.card.course {
  position: relative;
}
.card.course .card-image {
  border-bottom-width: 8px;
  border-bottom-style: solid;
  max-height: 174px;
  overflow: hidden;
}
.card.course .card-content {
  padding: 14px 17px 17px;
}
.card.course-stream-fs .card-image {
  border-color: #50d2ff;
}
.card.course .course-type {
  font-weight: 500;
  font-size: 12px;
  color: rgba(18, 18, 18, 0.5);
  text-transform: uppercase;
}
.card.course .course-title {
  font-weight: 500;
  font-size: 16px;
  color: #121212;
}
.card.course .course-info {
  padding: 0 17px;
  color: rgba(18, 18, 18, 0.5);
  font-size: 12px;
}
.card.course .course-info .row {
  border-top-width: 1px;
  border-top-style: solid;
  border-top-color: #e2e2e2;
  padding: 14px 0 0;
  margin: 0;
}
.card.course .course-info .row > div {
  padding: 0 0 14px;
}
.card.course .course-length {
  font-size: 14px;
  font-weight: 300;
  color: #121212;
}
.card.course .course-start {
  font-size: 14px;
  font-weight: 300;
  color: #121212;
}
.card.course .course-link {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
</style>
