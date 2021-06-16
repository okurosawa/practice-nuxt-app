<template>
  <v-row>
    <v-col v-for="film in films" :key="film.episodeID" cols="6">
      <v-card class="mx-auto my-6">
        <v-card-title>{{ film.title }}</v-card-title>
        <v-card-subtitle> ReleaseDate: {{ film.releaseDate }} </v-card-subtitle>
        <v-card-text>{{ film.openingCrawl }}</v-card-text>
        <v-card-actions>
          <v-btn primary block>Details</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: {
    allFilms: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {
      films: this.allFilms
    }
  },
  methods: {
    update() {
      this.films = this.allFilms.films
    }
  }
}
</script>
