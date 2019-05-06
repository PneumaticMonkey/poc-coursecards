<template>
  <v-container grid-list-md>
    <v-layout row wrap>
      <Card :course="course" v-for="course in data.nodeQuery.entities" v-if="course.fieldShowInCatalogue && course.entityPublished" v-bind:key="course.entityId" />
    </v-layout>
  </v-container>
</template>

<script>
  import Card from '~/components/course_card.vue'

  export default {
    components: {
      Card
    },
    async asyncData ({ app }) {
      const { data } = await app.$axios.$get('/courses.json');
      return {data};
    }
  }
</script>
