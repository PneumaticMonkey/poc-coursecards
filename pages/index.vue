<template>
  <div>
    <!-- <Banner />
    <CardFilters /> -->
    <v-container grid-list-lg class="card-grid">
      <v-layout row wrap>
        <Card :course="course" v-for="course in data.nodeQuery.entities" v-if="course.fieldShowInCatalogue && course.entityPublished" v-bind:key="course.entityId" />
      </v-layout>
    </v-container>
  </div>
</template>

<script>
  // import Banner from '~/components/Banner.vue'
  // import CardFilters from '~/components/CardFilters.vue'
  import Card from '~/components/CourseCard.vue'

  export default {
    components: {
      // Banner,
      // CardFilters,
      Card
    },
    async asyncData ({ app }) {
      const { data } = await app.$axios.$get('/courses.json');
      return {data};
    }
  }
</script>
