<template>  
  <section class="section" id="education">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="eduArea">
      <div class="eduCards">
        <div class="cardArea" v-for="(item,index) in cardInfo" :key="item.key" @click="switchPoint(index)">
          <img :src="item.src" class="eduIcon">
          <p class="schools">{{item.school}}</p>
          <span>{{item.depart}}</span>
        </div>
      </div>
      <div v-for="(item, index) in eduIntroArr" :key="item.key" class="eduIntro" :class="item.switch" >
        <div class="eduLetters">
          <p>{{item.letters}}</p>
        </div>
        <div class="edupics">
          <img :src="item.src" @click="linkFun(index)" :class="theImg">
          <p>{{item.imgInfo}}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return{
      theImg: 'hover',
      title:'Education',
      bgColor:'cardArea null',
      cardInfo:[
        {src:require('../assets/icon/eduCoding.svg'),school:'緯育TibaMe',depart:'前端工程師養成班'},
        {src:require('../assets/icon/graduation.svg') ,school:'臺灣師範大學',depart:'公民教育與活動領導學系-碩士班'},
        {src:require('../assets/icon/school.svg'),school:'彰化師範大學',depart:'體育學系 & 師資培育學程'},
      ],
      eduIntroArr:[
        {
          src:require('../assets/img/K.Smooth.jpg'),
          imgInfo:'程式專題發表',
          letters:
          `
          緯育TibaMe的課程主要以前端網頁設計為主。在課程的規劃下，學習過前端三劍客HTML、CSS、JavaScript，此階段以排版、RWD、DOM元件控制、事件物件、儲存機制等作為學習重點，並將以上所學技能在課程第一階段完成個人的專題網站，而我設計的是兒童學步車的官方購物網站，主要內容有產品購買、留言板、會員中心、購物車、小遊戲等頁面，很榮幸的在此階段獲得班上最佳RWD的殊榮；最後一個階段是學習Git版本控制、Vue.js、PHP、MySQL等技術，將其所學以團隊方式開發全端的網頁。
          `,
          switch:'on',
        },
        {
          src:require('../assets/img/conference.jpg'),
          imgInfo:'國際論文發表',
          letters:
          `
          師大研讀期間，多次針對教育科技領域之研究進行論文撰寫與發表，其中以眼動儀的相關應用為主要研究方向。過程中多次與同為碩士班的電機學系同仁合作，利用自行研發的機款進行準實驗研究。受試的對象從一般成人到高齡者，並結合不同形式的動態情境於實驗設計中，如自行車騎乘行為、影視觀賞行為等。此外，在團隊更是多次獲得國際研討會邀約，前往該國進行發表。
          `,
          switch:'off'
        },
        {
          src:require('../assets/img/malaysia.jpg'),
          imgInfo:'國際志工計畫',
          letters:
          `
          彰師大長期與馬來西亞偏鄉的中學合作，每年定期於彰師大進行教育人員徵選，派遣至馬國進行國際偏鄉育服務計畫。十分榮幸的，我在2013年獲選為種子教師，並前往PinHwa HighSchool Klang服務。在服務的過程中與當地的學生建立起深切的連結，即便是現在仍與當時的學生保持良好的聯繫。印象最深刻的是當年高3的陳同學，在我們積極的幫助下申請了臺灣的大學，並獲得馬來西亞的全額獎學金到台唸書。他本人也說，若不是我們的幫助他就只能在家鄉賣肉骨茶了。經過這樣的經驗，讓我深切的體會到偏鄉地區教育資源的困乏與不均。
          `,
          switch:'off'
        },
      ],
    }
  },
  methods: {
    switchPoint(index){
      this.eduIntroArr.forEach(function(item){
        item.switch = 'off';
      })
      this.eduIntroArr[index].switch = 'on';
      document.querySelectorAll('.cardArea').forEach(function(item){
        item.style='background-color:#00000000; border-radius:0px;'
      })
      document.querySelectorAll('.cardArea')[index].style= 'background-color:#0000002c; border-radius:20px;';
      if (index === 0) {
        this.theImg = 'hover'
      } else {
        this.theImg = 'nonHover'
      }
    },
    linkFun(index){
      if (index === 0) {
        window.open(' https://formula5041.github.io/K.Smooth/ ', 'K.Smooth')
      }
    }
  },
}
</script>

<style scoped> 
  .hover {
    cursor: pointer;
  }
  .eduArea{
    margin-top: 20px;
    width: 90%;
    padding: 20px;
    display: flex;
    flex-direction: column;
    border-radius: 10px;
    background-color: #189fb149;
  }
  .eduCards{
    display: flex;
    justify-content: center;
    width: 100%;
  }
  .cardArea{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    transition: all .5s;
    padding: 5px;
    width: 30%;
    margin: 10px;
    cursor: pointer; 
  }
  .cardArea:hover{
    background-color: #0000002c;
    border-radius: 20px;
  }
  .eduIcon{
    width: 60px;
    height: 60px;
  }
  .schools{
    color: chocolate;
    font-weight: bold;
    font-size: 26px;
    margin: 10px 0;
  }
  .eduIntro{
    margin-bottom: 10px;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    width: 100%;
    border: 0.1px solid black;
    border-radius: 10px;
    background-color: whitesmoke;
    padding:10px;
    transition: all .5s;
  }
  .on{
    display: flex;
  }
  .off{
    display: none;
  }
  /* Introdution of edu */
  .eduLetters{
    width: 60%;
    padding: 10px;
    display: flex;
    align-items: center;
  }
  .eduLetters p{
    word-wrap:break-word;
    line-height: 40px;
    font-size: 20px;
    padding-right: 10px;
    font-weight: 400;
    color: darkslategray;
  }
  .edupics{
    display: flex;
    flex-direction: column;
    justify-content: start;
    align-items: center;
    width: 40%;
    border-radius: 20px;
    margin-top: 36px;
  }
  .edupics img{
    width: 90%;
    border-radius: 10px;
  }
  .edupics p{
    font-size: 20px;
    color: #0b8080;
    font-weight: bold;
  }
  @media (max-width:450px) {
    .eduCards{
      flex-direction: column;
      align-items: center;
    }
    .cardArea{
      width: 100%;
    }
    .cardArea span {
      font-size: 12px;
    }
    .eduIcon{
      width: 40px;
      height: 40px;
    }
    .schools{
      font-size: 20px;
    }
    .eduIntro{
      flex-direction: column-reverse;
      align-items: center;
    }
    .eduLetters{
      width: 100%;
    }
    .eduLetters p{
      line-height: 32px;
      font-size: 16px;
      padding-right: 0;
      margin-top: 0;
    }
    .edupics{
      margin-top: 10px;
      width: 100%;
    }
    .edupics img{
      width: 100%;
    }
    .edupics p{
      font-size: 16px;
      color: #0b8080;
    }
  }
</style>