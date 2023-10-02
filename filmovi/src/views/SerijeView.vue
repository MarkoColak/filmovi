<template>
  <div>
    <div>
      <h1 style="color: #f9f9f9; padding-top: 50px">Serije: </h1>
      <v-row class="mb-6" no-gutters>
        <v-col v-for="(serija, index) in serije80" :key="index">
          <v-card class="serija-card">
            <v-img :src="serija.posterUrl" class="serija-image"></v-img>
            <v-card-title class="serija-title">{{ serija.title }}</v-card-title>
            <v-card-text>
              <div>
                <v-rating
                  v-model="serija.ocjena"
                  background-color="transparent"
                  class="serija-rating"
                  :precision="1"
                  :min="1"
                  :max="10"
                ></v-rating>
              </div>
            </v-card-text>
            <v-card-actions>
              <v-btn @click="spremiOcjenu(serija)">Spremi ocjenu</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      serije80: [
        {
          title: "The Tailor",
          posterUrl: "https://m.media-amazon.com/images/M/MV5BM2ZlNzk4ZGItZmNlYS00YzIyLTllMzItZTk1YzFjMmFlMWNmXkEyXkFqcGdeQXVyMTUzOTczNzYx._V1_.jpg",
          ocjena: null,
        },
        {
          title: "Burning Body",
          posterUrl: "https://m.media-amazon.com/images/M/MV5BNzQzYjAyNWEtM2U3Zi00MzNkLTg2YzEtN2M3NTc1MzEyOGNjXkEyXkFqcGdeQXVyMTUyMzg5NzM2._V1_.jpg",
          ocjena: null,
        },
        {
          title: "The Night Agent",
          posterUrl: "https://m.media-amazon.com/images/M/MV5BODgzYmFkZjAtYjhmNC00NDdkLTk4NGYtNDdiODVlNmE3ODkyXkEyXkFqcGdeQXVyNTE1NjY5Mg@@._V1_.jpg",
          ocjena: null,
        },
        {
          title: "Obsession",
          posterUrl: "https://m.media-amazon.com/images/M/MV5BZDQxMjg4MWUtZGUyNS00NTMzLWExNmItMGYwNzI4NWM3YjQ2XkEyXkFqcGdeQXVyMTUzMTg2ODkz._V1_.jpg",
          ocjena: null,
        },
        {
          title: "Top Boy",
          posterUrl: "https://pics.filmaffinity.com/Top_Boy_TV_Series-582175364-large.jpg",
          ocjena: null,
        },
        {
          title: "Dark",
          posterUrl: "https://m.media-amazon.com/images/M/MV5BOTk2NzUyOTctZDdlMS00MDJlLTgzNTEtNzQzYjFhNjA0YjBjXkEyXkFqcGdeQXVyMjg1NDcxNDE@._V1_.jpg",
          ocjena: null,
        },
      ],
    };
  },
  methods: {
  spremiOcjenu(serija) {
    if (serija.ocjena !== null) {
      alert(`Ocijenili ste seriju "${serija.title}" sa ocjenom ${serija.ocjena}`);
    } else {
      alert(`Niste ocijenili seriju "${serija.title}"`);
    }
  },
},
};
</script>

<style scoped>
.serija-card {
  background-color: #1a1a1a;
  max-width: 374px;
  margin: 0 auto 12px auto;
}

.serija-image {
  height: 250px;
}

.serija-title {
  color: #ffffff; /* Boja naslova serije */
}

.serija-rating {
  background-color: transparent; /* Boja ocjene serije */
  color: #ffffff;
}
</style>
