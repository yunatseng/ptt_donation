<template>
  <v-app>
    <v-app-bar app color="lime darken-4" dark>
      <h3 class="ml-2 title font-weight-light">
        PTT 超商挖眼案
      </h3>

      <v-spacer></v-spacer>

      <v-btn
        href="https://www.judicial.gov.tw/tw/cp-1888-658196-cc1ee-1.html"
        target="_blank"
        text
      >
        <span class="mr-2">最新判決</span>
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
        color="lime darken-4"
        class="white--text text-left"
        width="100%"
      >
        <v-card-text class="white--text">
          <ol>
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
          </ol>
        </v-card-text>

        <v-divider />

        <v-card-text class="white--text text-center">
          © {{ new Date().getFullYear() }} — Skylar
          <a
            href="mailto:yun.yuna.tseng@gmail.com"
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
     citeList: [{ url: 'https://zh.wikipedia.org/w/index.php?title=%E5%B1%8F%E6%9D%B1%E6%8C%96%E7%9C%BC%E6%A1%88&oldid=69168796', name: '屏東挖眼案. (2021, December 19). Retrieved from 維基百科, 自由的百科全書' },
      { url: 'https://www.ptt.cc/bbs/Gossiping/M.1633226685.A.2D7.html', name: '[問卦] 幹你娘，屏東挖眼案通通給我洗起來！' },
      { url: 'https://www.ptt.cc/bbs/Gossiping/M.1633333606.A.5F0.html', name: 'PTT 網友統計資料' },
       { url: 'https://www.freepik.com/vectors/woman-drawing', name: 'Woman drawing vector created by rawpixel.com - www.freepik.com' }]
  }),
};
</script>
