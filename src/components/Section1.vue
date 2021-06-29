<template>  
  <section class="home" id="home">
    <div class="imgContain">
      <img 
      class="headshot" 
      :src="headshots"
      v-on:click.enter="testAlert"
      >
    </div>
    <h1>{{fullname}}</h1>
    <span class="intro">I'm a Front-End developer</span>
    <ul class="social">
      <li v-for="item in social" :key="item.id">
      <a :href="item.link"><img v-bind:src="item.src" class="ii"></a>
      </li>
    </ul>
    <button v-on:click.enter="hireMe">Hire me</button>
    <div class="scrollDown">
      <a href="#about">
        <span class="downSpan">Scroll Down</span>
        <span class="downArea"></span>
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name:'Section1',
  data(){
    return{
      head:'NOM',
      fullname:'NOM NOM',
      hash:'#',  
      headshots: require('../assets/img/koala.jpg'),
      social:[
        {src: require('../assets/icon/gmail.svg'),link: 'https://tw.yahoo.com/',},
        {src: require('../assets/icon/instagram.svg'),link: 'https://tw.yahoo.com/',},
        {src: require('../assets/icon/facebook.svg'),link: 'https://tw.yahoo.com/',},
        {src: require('../assets/icon/line.svg'),link: 'https://tw.yahoo.com/',},
        {src: require('../assets/icon/twitter.svg'),link: 'https://tw.yahoo.com/',},
      ]
    }
  },
  methods: {
    testAlert: ()=>{
      alert('Oh! Don\'t touch me!')
    },
    hireMe: ()=>{
      alert('Please, Hire me!')
    },
    scrollDown: ()=>{

    }
  }
}
</script>

<style>
  .home{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .headshot{
    margin-top: 30%;
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 50%;
  }
  h1{
    margin: 0;
    color: white;
    font-size: 50px;
  }
  .intro{
    font-size: 18px;
    margin: 20px;
  }
  .social{
    display: flex;
    margin-bottom: 30px;
  }
  .social li{
    margin: 0 10px;
  }
  .social li a img{
    width: 35px;
    height: 35px;
  }
  .scrollDown{
    margin: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .scrollDown a{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  a span.downSpan {
    font-size: 20px;
    color: #faafaf;
  }
  a span.downArea{
    position: relative;
    margin-top: 5px;
    border: 1px solid white;
    border-radius: 30px;
    height: 80px;
    width: 40px;
    font-size: 40px;
    cursor: pointer;
  }
  a span.downArea::after {
    content: '.';
    position: absolute;
    left: 13px;
    bottom: 50px;
    animation-name: scrollMove;
    animation-duration: 2s;
    animation-fill-mode: forwards;
    animation-iteration-count: infinite;
  }
  @keyframes scrollMove{
    100%{
      transform: translateY(40px);
    }
  }
</style>