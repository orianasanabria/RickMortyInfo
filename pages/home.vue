<template>
  <v-row>
    <v-col cols="12" sm="3" v-for="(personaje, i) in personajes" :key="i">
      <v-card>
        <v-img height="250" :src="personaje.image"></v-img>

        <v-card-title>{{ personaje.name }}</v-card-title>
        <div class="px-4 pb-4">
          <v-chip-group column>
            <v-chip>{{ personaje.status }}</v-chip>
            <v-chip>{{ personaje.species }}</v-chip>
            <v-chip>{{ personaje.gender }}</v-chip>
          </v-chip-group>
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      personajes: [],
    }
  },
  methods: {
    async getData() {
      const url = 'https://rickandmortyapi.com/api/character'
      try {
        const req = await fetch(url)
        const response = await req.json()
        this.personajes = response.results
        console.log(response.results)
      } catch (error) {
        console.log(error)
      }
    },
  },
  created() {
    this.getData()
  },
}
</script>
