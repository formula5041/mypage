<template>
  <Head/>
  <main class="main">
    <Home/>
    <About/>
    <Education/>
    <Experience/>
    <Portfolio/>
    <h2 class="toTop" @click="toTheTop">To Top</h2>
  </main>
</template>

<script>
import Head from './components/Head.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Education from './components/Education.vue'
import Experience from './components/Experience.vue'
import Portfolio from './components/Portfolio.vue'

export default {
  name: 'App',
  components: {
    Head,
    Home,
    About,
    Education,
    Experience,
    Portfolio,

  },
  methods: {
    toTheTop(){
      window.scrollTo(0, 0)
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    scroll-behavior: smooth;
  }
  :root{
    --asidewidth: 300px;
  }
  a{
    text-decoration: none;
    color:white;
  }
  h1{
    color: chocolate;
  }
  ul{
    padding: 0;
    list-style: none;
  }
  html, body {
    background-color: #003e77;
    margin: 0;
  }
  .main{
    border-left: 1px solid white;
  }
  button{
    cursor: pointer;
    color: white;
    border: .5px solid #1a101094;
    border-radius: 30px;
    background-color: #afbb46;
    transition: all .5s;
    margin: 5px;
    width: 150px;
    height:50px;
    font-size: 28px;
  }
  button:hover{
    transform: translateY(-2px);
    background-color: #9e0404;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #f1f1f1;
  }
  .main{
    width: calc(100% - var(--asidewidth));
    margin-left: var(--asidewidth);
  }
  section{
    margin-bottom: 40px;
    padding:10px;
  }
  .toTop{
    width: 90%;
    text-align: end;
    cursor: pointer;
    transform: translateY(0px);
    animation-name: toTheTop;
    animation-duration: 2s;
    animation-fill-mode: forwards;
    animation-iteration-count: infinite;
  }
  @keyframes toTheTop{
    100%{
      transform: translateY(-10px);
    }
  }
  @media (max-width:450px) {
    :root{
      --asidewidth: 0px;
    }
    .main{
      border-left: 0px solid white;
    }
    button{
      width: 120px;
      height:40px;
      font-size: 18px;
    }
  }
</style>
