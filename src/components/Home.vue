<template>  
  <section class="home" id="home">
    <div class="imgContain">
      <img 
      class="headshot" 
      :src="headshots"
      >
    </div>
    <h1>{{fullname}}</h1>
    <span class="intro">1993 / 05 / 14</span>
    <span class="intro">I'm a Front-End developer</span>
    <ul class="social">
      <li v-for="item in social" :key="item.id">
      <a :href="item.link" target="_blank"><img v-bind:src="item.src" class="ii"></a>
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
  data(){
    return{
      fullname:'蔡昇宏',
      headshots: require('../assets/img/headshot.jpg'),
      social:[
        {src: require('../assets/icon/github.svg'),link: 'https://github.com/formula5041',},
        {src: require('../assets/icon/line.svg'),link: 'https://line.me/ti/p/uNhGAgErTu',},
        {src: require('../assets/icon/instagram.svg'),link: 'https://www.instagram.com/shenghung0514/?hl=zh-tw',},
        {src: require('../assets/icon/facebook.svg'),link: 'https://www.facebook.com/shenghung.tsai.1',},
        {src: require('../assets/icon/gmail.svg'),link: 'mailto:love61438@gmail.com',},
      ]
    }
  },
  methods: {
    hireMe: ()=>{
      alert('Please, Hire me!')
    },
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
    margin-top: 25%;
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