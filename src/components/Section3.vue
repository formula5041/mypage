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
  name:'Section3',
  data(){
    return{
      title:'Education',
      cardInfo:[
        {src:require('../assets/icon/graduation.svg') ,school:'臺灣師範大學',depart:'公民教育與活動領導學系-碩士班'},
        {src:require('../assets/icon/school.svg'),school:'彰化師範師大',depart:'體育學系 & 師資培育學程'},
        {src:require('../assets/icon/book.svg'),school:'瑞芳高工',depart:'綜合高中科'},
      ],
      eduIntroArr:[
        {
          src:require('../assets/icon/graduation.svg'),
          letters:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?',
          switch:'on'
        },
        {
          src:require('../assets/icon/school.svg'),
          letters:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?',
          switch:'off'
        },
        {
          src:require('../assets/icon/book.svg'),
          letters:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, incidunt nesciunt veniam quasi soluta dolorum cumque illo reprehenderit dolorem fugit. Nulla officia doloremque sit quis corrupti asperiores pariatur fuga itaque?',
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
    background-color: #df8c8c;
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
  }
  .eduLetters p{
    word-wrap:break-word;
    line-height: 30px;
  }
  .edupics{
    width: 40%;
    border-radius: 20px;
  }
</style>