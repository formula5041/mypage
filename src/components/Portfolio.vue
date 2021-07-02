<template>  
  <section class="section" id="portfolio">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="portfoArea">
      <div class="portfoList" >
        <ul >
          <li v-for="item in selectType" :key="item.key" @click="selectFun(item)">{{item}}</li>
        </ul>
      </div>
      <div class="portfoInfo">
        <div class="portfoItems" v-for="item in portfoContain" :key="item.id">
          <div class="portfoImgArea">
            <img class="portfoImgs" :src="item.icon">
            <div class="cover">
              <span class="typeName">{{item.type}}</span>
              <a :href="item.link" target="_blank"><h3>{{item.name}}</h3></a>
              <img class="Imgicon" :src="item.icon">
            </div>
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
      selectType:['All','Coding','Volunteer','Sports',],
      portfoContain:[
        {
          type:'Coding', 
          name:'K.Smooth', 
          icon: require('../assets/icon/coding.svg'),
          link: 'https://formula5041.github.io/tfd102-031/',
        },
        {
          type:'Coding', 
          name:'Taohilen', 
          icon: require('../assets/icon/coding2.svg'),
          link:'https://formula5041.github.io/taohilen/taohilen.html',
        },
        {
          type:'Volunteer', 
          name:'Malaysia', 
          icon: require('../assets/icon/volunteer.svg')
        },
        {
          type:'Volunteer', 
          name:'Canoe', 
          icon: require('../assets/icon/volunteer2.svg')
        },
        {
          type:'Sports', 
          name:'Media', 
          icon: require('../assets/icon/sport.svg')
        },
        {
          type:'Sports', 
          name:'Cycling', 
          icon: require('../assets/icon/sport2.svg')
        },
      ],
    }
  },
  methods: {
    selectFun(item){
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
      
      
    }
  },
}
</script>

<style>
  .portfoArea{
    margin-top: 20px;
    padding: 10px;
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
   .cover a {
     align-self: center;
     font-size: 24px;
   }
   .cover a h3{
     margin: 0;
   }
  .Imgicon{
    width: 20px;
    height: 20px;
    margin: 10px;
    margin-top: 0;
  }
</style>