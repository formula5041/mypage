<template>  
  <section class="section" id="about">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="myInfo">
      <div class="headshots">
        <img :src="headshots">
      </div>
      <div class="detailInfo">
        <div class="leftInfo">
          <span>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?</span>
          <button>Download CV</button>
        </div>
        <div class="rightInfo">
          <div 
            class="row" 
            v-for="(item, index) in skills" 
            :key="item"
          >
            <div class="up">
              <span class="lang">{{item.skill}}</span>
              <span class="per">{{item.percentage}}</span>
            </div>
            <div class="down">
              <div class="pOut">
                <p class="percent" :class="'percent'+(index+1)" >.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name:'Section2',
  data(){
    return{
      title:'About',
      headshots: require('../assets/img/koala.jpg'),
      skills:[
        {skill:'JavaScript',percentage:'95%',css:'percent1'},
        {skill:'MySQL',percentage:'70%',css:'percent2'},
        {skill:'PHP',percentage:'80%',css:'percent3'},
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

<style>
  /* Informations */
  .myInfo{
    display: flex;
    align-items: center;
    margin-top:40px;
    font-size: 24px;
  }
  .headshots{
    width: 30%;
    display: flex;
    justify-content: center;
    align-self: flex-start;
  }
  .headshots img{
    width: 150px;
    height: 150px;
    object-fit: cover;
    border-radius: 50%;
  }
  /* card */
  .detailInfo{
    width: 70%;
    display: flex;
    align-items: center;
    padding: 50px;
    padding-left: 25px;
    margin-right: 50px;
    border-radius: 10px;
    background-color: #189fb149;
  }
  .leftInfo{
    display: flex;
    flex-direction: column;
    width: 50%;
    font-size: 24px;
    margin-right: 20px;
  }
  .leftInfo button{
    width: 200px;
    margin: 20px;
  }
  /* skill */
  .rightInfo{
    display: flex;
    flex-direction: column;
    width: 50%;
    align-self: flex-start;
  }
  .row{
    margin-bottom: 20px;
  }
  .up{
    display: flex;
    justify-content: space-between;
  }
  .per{
    font-size: 18px;
    align-self: center;
  }
  .pOut{
    background-color: white;
    border-radius: 10px;
  }
  .percent {
    height: 12px;
    border-radius: 10px;
    color: #ffffff00;
    margin: 8px 0;
    transition: all 2s;
  }
  .percent1{
    background-color: #afbb46;
    width: 95%;
  }
  .percent2{
    background-color: #9e0404;
    width: 70%;
  }
  .percent3{
    background-color: #003e77;
    width: 80%;
  }
</style>