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
          para:
          `
          於聯網國際期間以業務身分接觸許多不同類型的專案，主要以軟體開發與活動規劃為大宗。其中
          `,
          img:require('../assets/img/topcycling.jpg'),
        },
        {
          year:'2018-2019',
          title:'洛特國際文化股份有限公司', 
          para:
          `
          洛特文化的主要工作為國際書展、嬰幼兒用品展的直接銷售，此外也針對客戶進行關係維護經營等業務。另外，中國大陸也是我們主要的服務範圍。公司不定期派員到各個省份參展，並開發地方市場。
          `,
          img:require('../assets/img/china.jpg'),
        },
        {
          year:'2016-2018',
          title:'國立臺灣師範大學', 
          para:
          `
          研究所畢業後留在師大執行
          `,
          img:require('../assets/img/german.jpg'),
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