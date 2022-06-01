<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>

        <Main />
   
    </v-main>

    <v-footer dark padless>
      <v-card
        flat
        tile
        color="primary"
        class="white--text text-left"
        width="100%"
      >
        <v-card-text class="white--text">
          <!-- <ol>
            <li v-for="(citation, i) in citeList" :key="i">
              <a
                :id="`event_${i}`"
                :tabindex="i"
                class="white--text footer-citation"
                :href="citation.url"
                target="_blank"
              >
                {{ citation.name }}
              </a>
            </li>
          </ol> -->
        </v-card-text>

        <v-divider />

        <v-card-text class="white--text text-center">
          © {{ new Date().getFullYear() }} — Skylar
          <a
            href="mailto:fav0124@gmail.com"
            target="_blank"
            rel="noopener noreferrer"
            ><v-icon>mdi-email</v-icon></a
          >
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Main,
  },
  data: () => ({
    //
  }),
};
</script>
