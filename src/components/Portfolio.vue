<template>  
  <section class="section" id="portfolio">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="portfoArea">
      <div class="portfoList" >
        <ul >
          <li class="liItems" v-for="(item, index) in selectType" :key="index.name" @click="selectFun(item, index)">{{item}}</li>
        </ul>
      </div>
      <div class="portfoInfo">
        <div class="portfoItems" v-for="item in portfoContain" :key="item.id">
          <a :href="item.link" target="_blank">
            <div class="portfoImgArea">
              <img class="portfoImgs" :src="item.icon">
              <div class="cover">
                <span class="typeName">{{item.type}}</span>
                <h3>{{item.name}}</h3>
                <img class="Imgicon" :src="item.icon">
              </div>
            </div>
          </a>
          <div>
            <p>{{item.type}}：{{item.name}}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return{
      title:'Portfolio',
      arrshow:false,
      selectType:['All','JS','Vue.js','API',],
      portfoContain:[
        {
          type:'JS', 
          name:'K.Smooth', 
          icon: require('../assets/icon/tricycle.svg'),
          link:'https://formula5041.github.io/K.Smooth/',
        },
        {
          type:'Vue.js', 
          name:'MyPage', 
          icon: require('../assets/icon/man.svg'),
          link:'https://formula5041.github.io/mypage/'
        },
        {
          type:'API', 
          name:'YouBike', 
          icon: require('../assets/icon/ubike.svg'),
          link:'https://formula5041.github.io/youbikeconnect/'
        },
      ],
    }
  },
  methods: {
    selectFun(item, index){
      let portfoItems = document.querySelectorAll('.portfoItems');
      portfoItems.forEach(value=>{
        value.style.display='flex';
      })
      if(item !== 'All'){
        let title = document.querySelectorAll('.typeName');
        title.forEach(value=>{
        if(value.innerHTML !== item)
          value.closest('.portfoItems').style.display='none';
        })
      }
      let liItems = document.querySelectorAll('.liItems');
      liItems.forEach( item=>{
        item.style.backgroundColor = '#00000023';
      })
      liItems[index].style.backgroundColor = 'chocolate';
    }
  },
}
</script>

<style>
  .portfoArea{
    margin-top: 20px;
    padding: 10px;
    /* height: 250px; */
    width: 90%;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #189fb149;
  }
  .portfoList {
    display: flex;
    align-self: flex-start;
  }
  .portfoList ul {
    margin: 4px 0;
    display: flex;
  }
  .portfoList ul li {
    margin: 0px 10px;
    cursor: pointer;
    background-color: #00000023;
    border-radius: 10px;
  }
  /* Info */
  .portfoInfo{
    display: flex;
    justify-content: center;
    width: 100%;
  }
  .portfoItems{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 30%;
    margin: 10px;
  }
  .portfoImgArea{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: white;
    position: relative;
    width: 250px;
    height: 150px;
  }
  @media screen and (max-width:1280px){
    .portfoImgArea{
      width: 200px;
    }
  }
  @media screen and (max-width:1080px){
    .portfoInfo{
      flex-direction: column;
      align-items: center;
    }
  }
  .portfoImgs{
    width: 50%;
    height:100%;
    padding: 10px;
  }
  /* Cover Setting */
  .cover{
    position: absolute;
    left: 0px;
    background-color: #040307;
    width: 100%;
    height: 100%;
    transition: all .5s;
    opacity: 0;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
   .cover:hover{
    opacity: .9;
   }
   .cover span{
     width: 80px;
     text-align: center;
     margin-left: 5px;
     background-color: rgb(134, 24, 43);
     border-radius: 0 0 5px 5px;
   }
   .cover h3{
    margin: 0;
    align-self: center;
    font-size: 28px;
   }
  .Imgicon{
    width: 20px;
    height: 20px;
    margin: 10px;
    margin-top: 0;
  }
  @media (max-width:450px) {
    .portfoList ul li {
      width: 50px;
      text-align: center;
    }
    .portfoInfo{
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: nowrap;
      width: 100%;
    }
    .portfoItems{
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      margin: 0px;
      margin-top: 20px;
    }
    .cover{
      opacity: .4;
    }
  }
</style>