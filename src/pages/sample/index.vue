<template>
  <v-layout>
    <films-list ref="filmList" :all-films="allFilms" />
  </v-layout>
</template>

<script>
import 'vue-apollo'
import getAllFilms from '~/apollo/queries/getAllFilms.gql'
import FilmsList from '~/components/FilmsList.vue'

export default {
  components: {
    FilmsList
  },
  data() {
    return {
      allFilms: []
    }
  },
  apollo: {
    allFilms: {
      prefetch: true,
      query: getAllFilms
    }
  },
  watch: {
    allFilms() {
      this.update()
    }
  },
  methods: {
    update() {
      this.$refs.filmList.update()
    }
  }
}
</script>
