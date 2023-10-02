<template>
  <div style="display: flex; justify-content: center; align-items: center; height: 100vh;">
    <v-form ref="form" v-model="valid" lazy-validation style="background-color: #000000; padding: 20px; width: 100%; max-width: 600px;">
      <h1 style="color: #5c6bc0">Kontaktirajte nas</h1>
      <v-text-field
        dark
        class="red--text"
        color="orange"
        v-model="name"
        :counter="50"
        :rules="nameRules"
        label="Ime"
        required
      ></v-text-field>

      <v-text-field
        dark
        v-model="last"
        color="orange"
        :counter="50"
        :rules="lastRules"
        label="Prezime"
        required
      ></v-text-field>

      <v-text-field
        dark
        color="orange"
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required
      ></v-text-field>

      <v-textarea
        dark
        color="orange"
        outlined
        label="Komentar"
        placeholder="Ostavite svoj komentar..."
      ></v-textarea>

      <v-checkbox
        dark
        v-model="checkbox"
        :rules="[(v) => !!v || 'Morate se složiti da biste nastavili!']"
        label="Slažem se"
        required
      ></v-checkbox>

      <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
        Prijava
      </v-btn>

      <v-btn color="error" class="mr-4" @click="reset"> Resetiraj </v-btn>

      <v-btn color="warning" @click="resetValidation"> Resetiraj validaciju </v-btn>
    </v-form>
  </div>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    last: "",
    lastRules: [
      (v) => !!v || "Name is required",
      (v) => (v && v.length <= 50) || "Name must be less than 10 characters",
    ],
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => (v && v.length <= 50) || "Name must be less than 10 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    select: null,
    checkbox: false,
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
      alert("Uspješno pohranjeno!");
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    },
  },
};
</script>
