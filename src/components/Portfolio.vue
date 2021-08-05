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
          name:'DropBeat', 
          icon: require('../assets/icon/song.svg'),
          link:'https://tibamef2e.com/tfd102/project/g1/'
        },
        {
          type:'Vue.js', 
          name:'MyPage', 
          icon: require('../assets/icon/man.svg'),
          link:'https://formula5041.github.io/mypage/'
        },
        {
          type:'Vue.js', 
          name:'Taohilen', 
          icon: require('../assets/icon/fish.svg'),
          link:'https://formula5041.github.io/taohilen/'
        },
        {
          type:'API', 
          name:'Weather', 
          icon: require('../assets/icon/weather.svg')
        },
        {
          type:'API', 
          name:'YouBike', 
          icon: require('../assets/icon/ubike.svg')
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
      // 還沒做完，接下來要
      let liItems = document.querySelectorAll('.liItems');
      // liItems.style.backgroundColor = '#00000023';
      liItems[index].style.backgroundColor = 'chocolate';
    }
  },
}
</script>

<style>
  .portfoArea{
    margin-top: 20px;
    padding: 10px;
    height: 400px;
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
    flex-wrap: wrap;
    width: 100%;
  }
  .portfoItems{
    display: flex;
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
</style>