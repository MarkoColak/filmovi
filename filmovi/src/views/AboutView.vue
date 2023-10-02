<template>
  <div>
    <v-card class="mx-auto" dark max-width="1000" style="background-color:#262626; border: 2px solid #3f51b5; border-radius: 10px;">
      <v-card-title style="padding-top: 20px;">
        <span class="text-h2 font-weight-bold" style="color: #ffffff;">O Filmu</span>
      </v-card-title>

      <v-card-text class="text-h6 font-weight-light" style="color: #ffffff;">
        Film je umjetnički izraz koji nas može inspirirati, razveseliti ili duboko dirnuti. Svaki film nosi svoju priču i poruku koju prenosi publici kroz slike, zvuk i emocije. Kao gledatelji, imamo priliku putovati u različite svjetove i doživjeti različite stvarnosti. Film nas povezuje i omogućuje nam da razmišljamo, sanjamo i osjećamo.
      </v-card-text>

      <div>
        <v-textarea
          outlined
          label="Podijelite svoje mišljenje o filmu"
          placeholder="Ostavite svoj komentar..."
          style="color: #ffffff;"
        ></v-textarea>
        <v-btn
          :loading="loading3"
          :disabled="loading3"
          color="#3f51b5"
          class="ma-2 white--text"
          @click="loader = 'loading3'"
        >
          Spremi
          <v-icon right dark>mdi-content-save</v-icon>
        </v-btn>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loading3: false,
    };
  },
};
</script>

<style scoped>
.text-h2 {
  font-size: 24px;
}

.text-h6 {
  font-size: 18px;
}

.font-weight-light {
  font-weight: 300;
}

.font-weight-bold {
  font-weight: 600;
}
</style>
