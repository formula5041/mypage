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
              <span class="picNote">{{item.picInfo}}</span>
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
          para:
          `
          於聯網國際期間以業務身分接觸許多不同類型的專案，主要以軟體開發與活動規劃為大宗。其中以教育部體育署的最讚亮點自行車道計畫為主要的業務。過程中除擔任與體育署窗口應對外，也與公司內部共同架設「自行車車道票選網站」。並在2020年舉辦一系列的「騎亮臺灣自行車活動」，到各個城市進行車道啟用儀式與領騎活動。
          `,
          img:require('../assets/img/topcycling.jpg'),
          picInfo: '*圖為實際網頁與擔任騎乘形象大使'
        },
        {
          year:'2018-2019',
          title:'洛特國際文化股份有限公司', 
          para:
          `
          洛特文化的主要工作是在各大「國際書展」、「嬰幼兒用品展」場內直接銷售，此外也針對客戶進行關係維護經營等業務。另外，中國大陸也是我們主要的服務範圍。因此公司不定期派員到各個省份參展，並開發地方市場。過去我也是時常前往大陸各省份的員工之一，舉凡北京、上海、廣州、雲南、陝西等...，因此間接的累積許多大陸市場接觸的經驗。
          `,
          img:require('../assets/img/china.jpg'),
          picInfo: '圖為北京國際書展中購買產品之客戶'
        },
        {
          year:'2016-2018',
          title:'國立臺灣師範大學', 
          para:
          `
          研究所畢業後留在師大執行教育部的專案計畫，主要的工作內容是與教授共同執行身心障礙者的輔導計畫、撰寫計劃書等內容。另外也將數個專案的執行成果撰寫成研究論文，並發表到國內外的研討會及期刊上。除了公部門計劃外，我們也向富邦文教提案，且獲得提升我國兒少媒體素養的專案計畫，並實參加「2018德國慕尼黑國際兒少影展」做一系列的專案研究，最後也將研究成果擬定成專門課程實際應用在我國兒少上。
          `,
          img:require('../assets/img/german.jpg'),
          picInfo: '圖為參與慕尼黑國際兒少影展圖'
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
     font-size: 28px;
   }
   .expdetail p{
     font-size: 20px;
     line-height: 40px;
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