<template>
  <v-container>
    <v-row>
      <v-col>
        <span class="white--text">{{ pages[0].Title }}</span>
        <img :src="api_url + pages[0].Photo[0].url" alt="">
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import pagesQuery from '~/assets/apollo/queries/pages/pages'

export default {
  data () {
    return {
      pages: Array,
      api_url: process.env.strapiBaseUri
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
