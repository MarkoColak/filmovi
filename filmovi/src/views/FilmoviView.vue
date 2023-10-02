<template>
  <div>
    <!-- Prikaz kartica filmova -->
    <v-row>
      <v-col v-for="(film, index) in filmovi" :key="index">
        <v-card>
          <v-img
            :src="film.posterUrl"
            height="400"
            class="grey lighten-2"
          ></v-img>
          <v-card-title>{{ film.title }}</v-card-title>
          <v-card-text>{{ film.description }}</v-card-text>
          <v-card-actions>
            <v-btn color="primary" @click="ocjeniFilm(film)">Ocijeni</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      filmovi: [
        {
          title: "The Batman",
          description: "",
          posterUrl: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSSkhG3dQyowasPMIk8m7MFLhVStbr9CndONi3cCtBnr6ZdIBSG6Md1Ezd45fJYMMgTtqw&usqp=CAU",
        },
        {
          title: "Minions: The Rise of Gru",
          description: "",
          posterUrl: "https://flxt.tmsimg.com/assets/p16982153_v_h9_ax.jpg",
        },
        {
          title: "Thor: Love and Thunder",
          description: "",
          posterUrl: "https://www.techadvisor.com/wp-content/uploads/2022/06/when-is-thor-love-and-thunder-available-to-stream.jpg?quality=50&strip=all&w=1024",
        },
        {
          title: "The Man from Toronto",
          description: "",
          posterUrl: "https://occ-0-64-999.1.nflxso.net/dnm/api/v6/6gmvu2hxdfnQ55LZZjyzYR4kzGk/AAAABfxgGluO8tGw6B2MGxnAMPK3Yv-AFR7UD9rH50mVD2cXmO8j-j_pEktM278hSC5_rx60GFNcmQxA6A9c9QGEg_D4gNhpzj0uqIgsHXwAZd2CnEl-yj4LlWbTNIckLxlMABV-jA.jpg?r=09c",
        },
      ],
    };
  },
  methods: {
    ocjeniFilm(film) {
      // Ovdje možete implementirati funkcionalnost za ocjenjivanje filma
      // Na primjer, možete otvoriti dijalog za unos ocjene ili nešto slično
      alert(`Ocijenili ste film "${film.title}"`);
    },
  },
};
</script>
