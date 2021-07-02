<template>  
  <section class="section" id="experience">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="expArea">
      <div class="expInfo" v-for="item in experienceList" :key="item.id">
        <div class="expLeft">
          <div class="line"></div>
          <div class="expList">
            <div class="expdetail">
              <span class="expTime">{{item.year}}</span>
              <h2>{{item.title}}</h2>
              <p>{{item.para}}</p>
              <span class="picNote">*圖片為工作時期相關相片</span>
            </div>
          </div>
        </div>
        <div class="expRight">
          <img class="expImg" :src="item.img">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return{
      title:'Experience',
      experienceList: [
        {
          year:'2019-2020',
          title:'聯網國際資訊股份有限公司', 
          para:'聯網國際成立於 1999 年 5 月，是國內網路行銷業界之先鋒、國內最大型之網路行銷公司，專精於協助客戶整合網路資源、規劃網路平台及數位行銷操作，包括網站規劃、網站經營、網路行銷、後台系統技術開發、網路媒體運用及網路活動執行等。聯網國際近二十年來，協助企業品牌建置並整合其網路行銷平台，專職於大型行銷網站平台規劃及製作、互動行銷操作與社群網站操作，透過整合企劃、創意與技術三大力量，忠實傳達企業品牌精神，提供貼進品牌形象的數位平台與行銷方案。',
          img:require('../assets/img/unit.jpg'),
        },
        {
          year:'2018-2019',
          title:'洛特國際文化股份有限公司', 
          para:'洛特國際文化成立於 1999 年 5 月，是國內網路行銷業界之先鋒、國內最大型之網路行銷公司，專精於協助客戶整合網路資源、規劃網路平台及數位行銷操作，包括網站規劃、網站經營、網路行銷、後台系統技術開發、網路媒體運用及網路活動執行等。聯網國際近二十年來，協助企業品牌建置並整合其網路行銷平台，專職於大型行銷網站平台規劃及製作、互動行銷操作與社群網站操作，透過整合企劃、創意與技術三大力量，忠實傳達企業品牌精神，提供貼進品牌形象的數位平台與行銷方案。',
          img:require('../assets/img/childrenbook.jpg'),
        },
        {
          year:'2016-2018',
          title:'國立臺灣師範大學', 
          para:'國立臺灣師範大學於 1928 年成立，是國內網路行銷業界之先鋒、國內最大型之網路行銷公司，專精於協助客戶整合網路資源、規劃網路平台及數位行銷操作，包括網站規劃、網站經營、網路行銷、後台系統技術開發、網路媒體運用及網路活動執行等。聯網國際近二十年來，協助企業品牌建置並整合其網路行銷平台，專職於大型行銷網站平台規劃及製作、互動行銷操作與社群網站操作，透過整合企劃、創意與技術三大力量，忠實傳達企業品牌精神，提供貼進品牌形象的數位平台與行銷方案。',
          img:require('../assets/img/college.jpg'),
        },
      ],
    }
  },
  methods: {
    
  },
}
</script>

<style>
  .expArea{
    margin-top: 20px;
    padding: 20px;
    width: 90%;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #189fb149;
  }
  .expInfo{
    margin-bottom: 50px;
    width: 100%;
    display: flex;
  }
  .expInfo:hover .expImg{
    opacity: 1;
  }
  /* Left Part */
  .expLeft{
    width: 50%;
    display: flex;
    position: relative;
  }
  .line{
    border-left: 1px solid tomato;
    margin: 20px 0;
    margin-right: 25px;
  }
   .line::before{
     content: '';
     position: absolute;
     background-image: url('../assets/icon/experience.svg');
     background-repeat: no-repeat;
     background-size: contain;
     width: 15px;
     height: 15px;
     top: 0;
     left: -6px;
   }
   .expdetail h2{
     color: tomato;
   }
  /* Right Part */
  .expRight{
    width: 50%;
    margin-left: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .expImg{
    width: 100%;
    border-radius: 10px;
    opacity: .7;
  }
  .picNote{
    color: tomato;
  }
</style>