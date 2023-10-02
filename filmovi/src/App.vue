<template>
  <v-app>
 
    <v-app-bar app dark color="#1976D2">
      <v-app-bar-nav-icon @click="drawer = !drawer" style="color: rgb(255, 255, 255)"></v-app-bar-nav-icon>
      <v-toolbar-title class="font-weight-bold white--text" style="position: absolute; left: 50%; transform: translateX(-50%);">
        MOVIES
      </v-toolbar-title>
      <v-btn icon href="/" style="color: rgb(255, 255, 255)">
        <v-icon>mdi-home</v-icon>
      </v-btn>
    </v-app-bar>
    

    <!-- Logo and title start -->
    <v-navigation-drawer v-model="drawer" app color="#1976D2">
      <v-sheet>
        <v-list
          style="
            margin-top: -10px;
            margin-bottom: -10px;
            background-color: #000000;
          "
        >
          <v-list-item>
            <v-list-item-icon>
              <v-img
                src="https://img.icons8.com/external-febrian-hidayat-gradient-febrian-hidayat/2x/external-popcorn-fast-food-febrian-hidayat-gradient-febrian-hidayat.png"
                height="40px"
                width="40px"
                style="margin-right: 10px"
              ></v-img>
            </v-list-item-icon>
            <v-list-item-content class="font-weight-thin">
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-sheet>
      <!-- Logo and title end -->

      <v-divider></v-divider>

      <!-- Navigation start -->
      <v-list rounded flat>
        <v-list-item
          v-for="[icon, text, route] in links"
          :key="icon"
          :to="route"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title id="li">{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- Navigation end -->

    <!-- Main section start -->
    <v-main>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    links: [
      ["mdi-home", "Home", "/"],
      ["mdi-movie-roll", "Serijes", "/serije"],
      ["mdi-movie-open", "Movies", "/filmovi"],
      ["mdi-information-outline", "About", "/about"],
      ["mdi-card-account-mail", "Contact", "/contact"],
    ],
  }),
};
</script>
