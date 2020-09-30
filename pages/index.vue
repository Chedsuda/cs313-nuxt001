<template lang="html">
  <div>
    <v-text-field v-model="query" label="SEARCH" />
    <v-btn depressed color="#69F0AE" @click="handleSearchNasa">
      <v-icon dark>
        mdi-plus
      </v-icon>
      Search
    </v-btn>
    <br><br>
    <v-row justify="center">
      <v-card
        v-for="list in nasa"
        :key="list.items"
        width="344"
        class="ml-6 mb-6"
      >
        <nuxt-link :to=" {name: 'product-id', params: { id: list }} ">
          <v-img :src="list.links[0].href" height="194" />
        </nuxt-link>
      </v-card>
    </v-row>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      query: '',
      nasa: ''
    }
  },
  methods: {
    handleSearchNasa () {
      const url = 'https://images-api.nasa.gov/search?q=' + this.query + ''
      axios.get(url).then((response) => {
        this.nasa = response.data.collection.items.slice(0, 36)
      })
    }
  }
}
</script>
