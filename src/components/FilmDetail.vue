<template>
  <v-row justify="center">
    <v-dialog max-width="500">
      <v-card>
        <v-card-title class="text-h5">
          Use Google's location service?
        </v-card-title>

        <v-card-text>
          {{ film }}
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn color="green darken-1" text @click="dialog = false">
            Disagree
          </v-btn>

          <v-btn color="green darken-1" text @click="dialog = false">
            Agree
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
import 'vue-apollo'
import getFilm from '~/apollo/queries/getFilm.gql'

export default {
  props: {
    filmDialog: {
      type: Boolean,
      default: false
    },
    filmId: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      dialog: false,
      film: {},
      id: ''
    }
  },
  apollo: {
    film: {
      prefetch: false,
      query: getFilm,
      variables: {
        id: 'ZmlsbXM6MQ=='
      }
    }
  },
  watch: {
    filmId() {
      this.update()
    }
  },
  method: {
    update() {
      this.id = this.filmId
    }
  }
}
</script>
