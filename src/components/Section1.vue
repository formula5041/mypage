<template>  
  <section class="home">
    <img 
      class="headshot" 
      src="../assets/img/catrun.png"
      v-on:click.enter="testAlert"
    >
    <h1>{{fullname}}</h1>
    <span>I'm a Front-End developer</span>
    <ul class="social">
      <li v-for="item in social" :key="item.id">
      <a :href="item.link"><img v-bind:src="item.src" class="ii"></a>
      </li>
    </ul>
    <button v-on:click.enter="hireMe">Hire me</button>
    <div class="scroll-down">
      <span>Scroll Down</span>
      <a href="#"></a>
    </div>
  </section>
</template>

<script>
export default {
  name:'Section1',
  data(){
    return{
      head:'Cat',
      fullname:'JIBAN MEOW',
      hash:'#',  
      social:[
        {src: require('../assets/icon/gmail.svg'),link: 'https://tw.yahoo.com/',},
        {src: require('../assets/icon/facebook.svg'),link: 'https://tw.yahoo.com/',},
        {src: require('../assets/icon/instagram.svg'),link: 'https://tw.yahoo.com/',},
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
  h1{
    margin: 0;
    color: white;
  }
  .home{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .headshot{
    width: 150px;
    height: 150px;
    object-fit: cover;
    border-radius: 100%;
  }
  .social{
    display: flex;
  }
  .social li{
    margin: 0 10px;
  }
  .social li a img{
    width: 20px;
    height: 20px;
  }
</style>