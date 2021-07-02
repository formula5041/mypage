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
          <p>{{item.school}}</p>
          <span>{{item.depart}}</span>
        </div>
      </div>
      <div v-for="(item) in eduIntroArr" :key="item.key" class="eduIntro" :class="item.switch" >
        <div class="eduLetters">
          <p>{{item.letters}}</p>
        </div>
        <img :src="item.src" class="edupics">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return{
      title:'Education',
      cardInfo:[
        {src:require('../assets/icon/graduation.svg') ,school:'臺灣師範大學',depart:'公民教育與活動領導學系-碩士班'},
        {src:require('../assets/icon/school.svg'),school:'彰化師範大學',depart:'體育學系 & 師資培育學程'},
        {src:require('../assets/icon/book.svg'),school:'瑞芳高工',depart:'綜合高中科'},
      ],
      eduIntroArr:[
        {
          src:require('../assets/icon/graduation.svg'),
          letters:'師大，是位於中華民國臺北市的綜合型大學，是亞洲著名師範大學。前身為1922年創立的臺灣總督府臺北高等學校，後改制為師範學校，並逐步從學院改大學、從省立改國立。',
          switch:'on'
        },
        {
          src:require('../assets/icon/school.svg'),
          letters:'彰師大，為彰化市的一所師範大學，為臺灣三所師範大學之一，該校前身為1971年創立的臺灣省立教育學院（簡稱省教院），共有進德校區和寶山校區兩個校區；現設有8個學院（含進修學院）、40多個各學術領域之研究中心與數百個實驗室，以及附屬幼兒園、彰師附工等附屬機構。以教育、理工、語言科系立校，輔導、心理諮商、特殊教育等領域則為全臺灣的發源地。',
          switch:'off'
        },
        {
          src:require('../assets/icon/book.svg'),
          letters:'本校創立於日治時期昭和9年2月(民國23年2月)(西元1934年)，由日本總督府敕任技師八田與一、日本教育家西村仁三郎、省籍教育家曹賜寤及林熊洋等人共同創立。',
          switch:'off',
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
    },
  },
}
</script>

<style>
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
    padding: 5px;
    width: 30%;
    margin: 10px;
    cursor: pointer;
  }
  .eduIcon{
    width: 40px;
    height: 40px;
  }
  .eduIntro{
    margin-bottom: 10px;
    display: flex;
    width: 100%;
    border: 0.1px solid black;
    border-radius: 10px;
    background-color: #aabedd;
    padding:10px;
    color:black;
    padding: 10px;
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
    line-height: 30px;
    font-size: 22px;
    padding-right: 10px;
    color: #07041f;
  }
  .edupics{
    width: 40%;
    border-radius: 20px;
  }
</style>