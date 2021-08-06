<template>  
  <section class="section" id="about">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="myInfo">
      <div class="detailInfo">
        <div class="leftInfo">
          <div v-for="item in aboutMe" :key="item.title"> 
            <h3 class="aboutTitle">{{item.title}}</h3>
            <span class="info">{{item.info}}</span>
          </div>
          <button><a href="https://drive.google.com/file/d/12vXJgFboOB0zlGFHLeG_SYtQXxXychAB/view?usp=sharing" target="_blank"> More About</a></button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return{
      title:'About',
      headshots: require('../assets/img/koala.jpg'),
      skills:[
        {skill:'JavaScript',percentage:'95%',css:'percent1'},
        {skill:'MySQL',percentage:'70%',css:'percent2'},
        {skill:'PHP',percentage:'80%',css:'percent3'},
      ],
      aboutMe: [
        {
          title:'[求學階段的我]',
          info: 
          `
          國小開始，一路都在體育環境長大，經歷「只要你還沒死，都要繼續練」的愛之教育，因此造就了堅忍無比的意志。
          彰師大是我的人生轉捩點，認識了一位專注於生命教育與研究的師長，學習到「生命的價值與知識的渴望」，也因如此，大三開始奮發攻讀研究所考試，開啟了教育研究之路。
          進入碩班的我，很榮幸的與崇拜已久的師長進入到同間學校-臺師大，我也順利的成為他門下的弟子。持續與他學習的我們一起共同經歷了我的碩論、無數個專案計畫、國內外研討會，甚至錄製廣播、電視臺節目、國際影展...。過程雖然受益良多，但我自知不能永遠待在這保護傘底下過。
          `,
        },
        {
          title:'[工作階段的我]',
          info: 
          `
          離開師大後，告訴自己30歲以前一定要找到人生中第一節後 (籃球賽術語) 的3/4場！於是我經歷了幼兒教材銷售、活動公司業務、自家產品販售，過程發現，這些都是很有意思的產業，但他們都有兩個共通點。
          一，環境限制：少子化銷售量減少、疫情限制活動、疫情限制人流下降。
          二、網路資訊化：以上的三間(含自家產品銷售)都還活著，皆賴於網路資訊。由此證明該領域對現在與未來的重要性。
          `,
        },
        {
          title:'[現在的我]',
          info: 
          `
          承如上述，我便利馬報名了緯育Tibame，前端網頁設計課程，展開了軟體工程的學習之路。幾個月下來，每日投入許多時間在Coding上，雖然偶而卡關有些疲憊，但更多的時候是感到無比的渴望，希冀習得更多未知的程式語法與解決更多的難題。
          `,
        },
        {
          title:'[求學階段的我]',
          info: 
          `
          我想，我找到人生第一節後的3/4場了，首先我要成為「前端工程師」，然後再一步一步的掌握更多的IT技術。往每天都比昨天的自己更進步的工程師邁進。
          `,
        },
      ],
      windowH:0,
    }
  },
  methods: {

  },
  mounted(){
    let about = document.querySelector('#about');
    // console.log(about.clientHeight);
    if(about.clientTop == 0){
      // console.log('11');
    }
    // console.log(window.pageYOffset);
    // this.windowH += 1;
    // console.log(this.windowH);
  },
}
</script>

<style scoped>
  /* Informations */
  .myInfo{
    display: flex;
    align-items: center;
    margin-top:40px;
    font-size: 24px;
    justify-content: center;
  }
  /* card */
  .detailInfo{
    width: 90%;
    display: flex;
    align-items: center;
    padding: 50px;
    padding-left: 25px;
    border-radius: 10px;
    background-color: #189fb149;
  }
  .leftInfo{
    display: flex;
    flex-direction: column;
    width: 100%;
    font-size: 24px;
    margin-right: 20px;
  }
  .leftInfo button{
    width: 200px;
    margin-left: 0px;
    margin-top: 30px;
  }
  .aboutTitle {
    /* color: chocolate; */
    color: chocolate;
    font-weight: bold;
  }
  .info{
    color: aliceblue;
    font-size: 22px;
    line-height: 40px;
  }
</style>