<template>
  <v-container fluid>
    <v-row>
      <v-img
        class="white--text"
        src="@/assets/ptt_banner.jpg"
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
      <v-col
        cols="12"
        style="background-size: cover"
        :style="{ backgroundImage: `url(${require('@/assets/bg.jpg')})` }"
      >
        <v-carousel
          cycle
          height="800"
          hide-delimiter-background
          show-arrows-on-hover
        >
          <v-carousel-item v-for="(slide, i) in slides" :key="i">
            <v-sheet color="#d3c9cb3d" height="100%">
              <v-row class="fill-height" style="flex-wrap: nowrap;margin:30px"  justify="center">
                <div class="text-h6" style="width: 40%; ">作者：{{ slide.author }}</div>
                <div class="text-body-1" style="width: 45%;">
                  {{ slide.final_text }}
                </div>
              </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Main",

  data: () => ({
    slides: [
      {
        author: "grace0523 (小小)",
        date: "Tue Oct  5 12:50:27 2021",
        final_text:
          "會攻擊人的神經病真的很可惡！  是不是要找一個外島把神經病都關在那  另外雖然捐的不多  但祝小妹妹能早日康復！    https://i.imgur.com/CkEI42A.jpg  ※ 引述《lovea》之銘言 : 幹，屏東挖眼案這麼嚴重的事 : 你們這些小朋友還在那邊洗啥雜魚的恩怨情仇 : 有沒有搞錯????? : 還有花蓮大樓倒塌，絕對要深究責任 : 別被塔綠班給蒙混過去了 : 通通給我洗起來！  ",
      },
      {
        author: "prettypaty (喵電感應)",
        date: "Tue Oct  5 12:46:19 2021",
        final_text:
          "本小妹只是個研究生，一個月薪水有限 略盡棉薄之力，拋磚期待引來更多的玉  https://i.imgur.com/3IMElmG.jpg  昨天看到一篇文說 鄉民這樣的捐款也無助於改善思覺失調症患者的治療與救治，沒有什麼意義 但我們也只是老百姓，我們用選票選出這個政府 讓這個政府召集專家解決問題，這責任不該落在百姓身上吧 在我們能力可及的範圍，我們能做的就是用金錢和物質支持受害者了 祝福潘小姐早日康復  ",
      },
      {
        author: "wwman (記憶拼圖)",
        date: "Tue Oct  5 12:45:50 2021",
        final_text:
          " 推這篇 幹 最近幾天在吵/炒什麼 狗屁小事情  什麼龍跟k ptt用戶都三十幾歲了 這種小事  還要花幾百篇去討論 真的很無言  就兩個小咖 各自的立場 價值觀 信仰有差別  有必要討論誰是絕對的對錯 跟挖以前的事蹟?     我覺得社會安全網 要社工+配兩便衣警察支援   去跟精神暴力者去家訪或調查時 全程攝影 必要時可以開槍   然後要政府要開設 收治收容的隔絕醫療環境   收治收容 有達標 無法跟正常社會活動的暴力精神者   監獄中度輕度犯人    可以在裡面工作比如 收容院的便利商店店員   或者請犯人在收容院裡面當職工 以獲得減刑   讓暴力精神者 有中度或輕度自由 但不能出去   社會社區去做可能犯罪 要有絕對高程度隔絕  的收治   讓精神暴力者在裡面 有隔絕的小型社區 跟小型環境   監獄犯人可以申請當員工   來獲得減刑  收治社區可參考外國 可以養寵物狗貓 等等各種可以調適身心的實驗作法   外國的對監獄或者精神者有很多實驗作法 (這邊不是很確定 但好像有些是以前電視   或網路上新聞看過的做法)   比如 養寵物   或者       輕音樂治療 或者 香精+寧靜藥物治療   或者可以訓練互動的團體遊戲 等等   請後面高手再推文補上吧   以上是我對社會安全網     簡略的建議      請大家可以補強跟討論~~   排版有點亂  請原諒 謝謝大家~  ",
      },
      {
        author: "shaoyanyan (小鹽)",
        date: "Tue Oct  5 12:42:45 2021",
        final_text:
          "https://i.imgur.com/sJP9k2T.jpg  捐款給她捐起來啦！ 幹你娘塔綠班去死！ 有症腐會做事! 相信症腐相信黨（個屁）！  ",
      },
    ],
  }),
};
</script>
