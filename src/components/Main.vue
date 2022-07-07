<template>
  <v-container fluid>
    <v-row>
      <v-img
        class="white--text"
        src="../assets/ptt_banner.jpg"
        gradient="to top right, rgba(15,15,18,.5), rgba(25,25,30,.8)"
        :lazy-src="`https://picsum.photos/10/6?image=1`"
        :height="$vuetify.breakpoint.smAndDown ? '100%' : '400'"
      >
        <template v-slot:placeholder>
          <v-row class="fill-height ma-0" align="center" justify="center">
            <v-progress-circular indeterminate color="grey lighten-5" />
          </v-row>
        </template>
        <v-container class="fill-height">
          <v-row
            align="center"
            :class="$vuetify.breakpoint.smAndDown ? 'pl-4 pr-6' : ''"
          >
            <div class="text-lg-h3 text-md-h3 text-h5 font-weight-regular">
              PTT 超商挖眼案 捐款紀錄
            </div>
            <v-row justify="center">
              <div class="text-lg-h5 text-md-h5 font-weight-light ml-3">
                Sep 26, 2021
              </div>
            </v-row>
          </v-row>
        </v-container>
      </v-img>
    </v-row>

    <v-row>
      <v-col cols="12">
        <div :style="{ backgroundImage:  `url(${require('@/assets/bg.jpg')})` }">
        <div
          class="font-weight-bold title mb-2 text-center"
          :class="{'':$vuetify.breakpoint.smAndDown}"
        >
          僅列舉 109~110 年部分事故
        </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Main",

  data: () => ({
    ecosystem: [
      {
        text: "vuetify-loader",
        href: "https://github.com/vuetifyjs/vuetify-loader",
      },
      {
        text: "github",
        href: "https://github.com/vuetifyjs/vuetify",
      },
      {
        text: "awesome-vuetify",
        href: "https://github.com/vuetifyjs/awesome-vuetify",
      },
    ],
    importantLinks: [
      {
        text: "Documentation",
        href: "https://vuetifyjs.com",
      },
      {
        text: "Chat",
        href: "https://community.vuetifyjs.com",
      },
      {
        text: "Made with Vuetify",
        href: "https://madewithvuejs.com/vuetify",
      },
      {
        text: "Twitter",
        href: "https://twitter.com/vuetifyjs",
      },
      {
        text: "Articles",
        href: "https://medium.com/vuetify",
      },
    ],
    whatsNext: [
      {
        text: "Explore components",
        href: "https://vuetifyjs.com/components/api-explorer",
      },
      {
        text: "Select a layout",
        href: "https://vuetifyjs.com/getting-started/pre-made-layouts",
      },
      {
        text: "Frequently Asked Questions",
        href: "https://vuetifyjs.com/getting-started/frequently-asked-questions",
      },
    ],
  }),
};
</script>
