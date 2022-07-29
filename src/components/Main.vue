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
                class="fill-height pa-6 pa-md-15 justify-space-evenly justify-md-center"
                :class="{'flex-column':$vuetify.breakpoint.smAndDown}"
                style="flex-wrap: nowrap; "
                
              >
                <div class="text-md-h6" :class="{'carousel-text1':$vuetify.breakpoint.smAndDown}" style="width: 40%; text-align: center">
                  作者：{{ slide.author }}<br />
                  {{ slide.date }}
                </div>
                <div
                  class="text-md-subtitle-1"
                  :class="{'carousel-text2':$vuetify.breakpoint.smAndDown}"
                  style="width: 52%; "
                >
                  {{ textWithoutUrl(slide.final_text) }}
                  <div
                    style="text-align: center"
                    v-if="textImgUrl(slide.final_text).length > 0"
                  >
                    <img
                      style="width: 40%; margin-top: 50px;margin-left:10px"
                      :class="{'carousel-img':$vuetify.breakpoint.smAndDown}"
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
                class="related-links"
                href="https://drive.google.com/file/d/103ddeuTXk4tA3R38unoXdotlxYCEWbCd/view"
                >民間版《精神衛生法》說明及全文</a
              >
            </li>
            <li>
              <a
                class="related-links"
                href="https://isbn.ncl.edu.tw/NEW_ISBNNet/main_DisplayRecord.php?&Pact=Display&Pstart=1"
                >正常與瘋狂的天秤: 談精神疾病與司法鑑定</a
              >
            </li>
            <li>
              <a
                class="related-links"
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
                class="related-links"
               
                href="https://www.cna.com.tw/news/firstnews/202111210025.aspx"
                >超商店員疑勸戴口罩遭刺死 犯嫌遭羈押</a
              >
            </li>
            <li>
              <a
                class="related-links"
                href="https://www.cna.com.tw/news/asoc/202110200372.aspx"
                >未戴口罩被提醒惱羞毆打超商店員顧客 桃園男送辦</a
              >
            </li>
            <li>
              <a
                class="related-links"
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
import PTT_DATA  from '../data/data';
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
   
  }),
  computed:{
    slides(){
      return this.shuffleArray(PTT_DATA).slice(0,14)
    }
  },
  methods: {
    shuffleArray(inputArray){
      inputArray.sort(()=> Math.random() - 0.5);
      return inputArray
    },
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
  font-weight: bold;
  height: 60px;
}
.carousel-text2{
  margin-top: 15px;
  width: 100% !important;
  font-size: 16px !important;
}
.carousel-img{
  width: 60% !important;
  margin-top: 30px !important;
  margin-left:0 !important
}
.related-links{
  font-style: 14px;
  color: #231306 !important
}
</style>
