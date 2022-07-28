<template>
  <v-container fluid>
    <v-row>
      <v-img
        class="white--text"
        src="@/assets/ptt_banner2.jpg"
        gradient="to top , rgba(181, 169, 146,.65), rgba(59, 56, 11,.8)"
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
            style="justify-content: center;"
          >
            <div
              class="ma-5 text-subtitle-1 text-md-h3"
              :class="{ 'text-center': $vuetify.breakpoint.smAndDown }"
            >
              PTT 超商挖眼案 捐款紀錄
            </div>
            
              <div class="text-subtitle-1 text-md-h5">
                Sep 26, 2021
              </div>
      
          </v-row>
        </v-container>
      </v-img>
    </v-row>
    <v-row>
      <v-col
        cols="12"
        style="background-color: #ccc5be; color: #3e3a35"
      >
        <div class="ma-5 ma-md-16 text-center">
          <v-alert
            outlined
            color="lime darken-4"
            class="text-subtitle-1 text-md-h6"
          >
            2021 年 9 月 26
            日，屏東縣一名女性超商店員因提醒楊姓男子戴口罩、別在店門口抽菸，遭男子攻擊臉部且遭徒手挖眼¹。<br />
            2021 年 10 月 3 日，一篇標題為「 [問卦]
            幹你娘，屏東挖眼案通通給我洗起來！」的 PTT 文章² 由網友 lovea 首 Po
            後開始發酵，截至目前（2022/07/01）共有
            <strong>1209</strong>
            篇回文，其中更不乏眾多熱心鄉民捐款³，為的就是希望能幫助到該名超商女店員。</v-alert
          >
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        cols="12"
        style="background-size: cover"
        :style="{ backgroundImage: `url(${require('@/assets/bg.jpg')})` }"
      >
        <v-carousel
          cycle
          height="850"
          hide-delimiter-background
          show-arrows-on-hover
        >
          <v-carousel-item v-for="(slide, i) in slides" :key="i">
            <v-sheet color="#d3c9cb3d" height="110%">
              <v-row
                class="fill-height pa-6 pa-md-15"
                :class="{'flex-column':$vuetify.breakpoint.smAndDown}"
                style="flex-wrap: nowrap; "
                justify="center"
              >
                <div class="text-h6" :class="{'carousel-text1':$vuetify.breakpoint.smAndDown}" style="width: 40%; text-align: center">
                  作者：{{ slide.author }}<br />
                  {{ slide.date }}
                </div>
                <div
                  class="text-subtitle-1"
                  :class="{'carousel-text2':$vuetify.breakpoint.smAndDown}"
                  style="width: 52%; "
                >
                  {{ textWithoutUrl(slide.final_text) }}
                  <div
                    style="text-align: center"
                    v-if="textImgUrl(slide.final_text).length > 0"
                  >
                    <img
                      style="width: 40%; margin-top: 50px"
                      v-for="(url, i) in textImgUrl(slide.final_text)"
                      :key="i"
                      :src="textImgUrl(slide.final_text)[i]"
                      alt="圖片"
                    />
                  </div>
                </div>
              </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" style="background-color: #ccc5be">
        <div class="ma-5 ma-md-16 text-center">
          <v-alert
            outlined
            color="lime darken-4"
            class="text-subtitle-1 text-md-h6"
            >延伸閱讀</v-alert
          >
        </div>
        <v-alert text color="lime darken-4" border="left">
          <p><strong>相關法條討論</strong></p>
          <ul>
            <li>
              <a
                style="color: #231306"
                href="https://drive.google.com/file/d/103ddeuTXk4tA3R38unoXdotlxYCEWbCd/view"
                >民間版《精神衛生法》說明及全文</a
              >
            </li>
            <li>
              <a
                style="color: #231306"
                href="https://isbn.ncl.edu.tw/NEW_ISBNNet/main_DisplayRecord.php?&Pact=Display&Pstart=1"
                >正常與瘋狂的天秤: 談精神疾病與司法鑑定</a
              >
            </li>
            <li>
              <a
                style="color: #231306"
                href="https://law.moj.gov.tw/LawClass/LawAll.aspx?pcode=L0020030"
                >現行精神衛生法條文</a
              >
            </li>
          </ul>
          <v-divider style="margin: 18px" />

          <p><strong>相關新聞</strong></p>
          <ul>
            <li>
              <a
                style="color: #231306"
                href="https://www.cna.com.tw/news/firstnews/202111210025.aspx"
                >超商店員疑勸戴口罩遭刺死 犯嫌遭羈押</a
              >
            </li>
            <li>
              <a
                style="color: #231306"
                href="https://www.cna.com.tw/news/asoc/202110200372.aspx"
                >未戴口罩被提醒惱羞毆打超商店員顧客 桃園男送辦</a
              >
            </li>
            <li>
              <a
                style="color: #231306"
                href="https://www.cna.com.tw/news/asoc/202110270059.aspx"
                >不滿被要求戴口罩 台中醉男毆打店員遭法辦</a
              >
            </li>
          </ul>
        </v-alert>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" style="background-color: #ccc5be">
        <div id="disqus_thread"></div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
/**
 *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
 *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
/*
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    */
(function () {
  // DON'T EDIT BELOW THIS LINE
  var d = document,
    s = d.createElement("script");
  s.src = "https://ptt-1.disqus.com/embed.js";
  s.setAttribute("data-timestamp", +new Date());
  (d.head || d.body).appendChild(s);
})();

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
  methods: {
    textWithoutUrl(text) {
      const textArr = text.split(" ");
      const plainText = textArr.filter(
        (i) => !(i.includes("http") || i.length === 0)
      );
      return plainText.join(" ");
    },
    textImgUrl(text) {
      const textArr = text.split(" ");
      const imgUrl = textArr.filter((i) => i.includes("http"));
      return imgUrl;
    },
  },
};
</script>
<style>
a {
  text-decoration: none;
}
.carousel-text1{
  font-size: 18px !important;
  width: 100% !important;
}
.carousel-text2{
  margin-top: 15px;
  width: 100% !important;
  font-size: 16px !important;
}
</style>
