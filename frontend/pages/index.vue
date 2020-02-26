<template>
  <v-container>
    <v-row>
      <v-col>
        <span class="white--text">{{ pages }}</span>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import pagesQuery from '~/assets/apollo/queries/pages/pages'

export default {
  data () {
    return {
      pages: []
    }
  },
  apollo: {
    pages: {
      prefetch: true,
      query: pagesQuery
    }
  }
}
</script>
