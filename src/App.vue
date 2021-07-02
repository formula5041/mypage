<template>
  <Head/>
  <main class="main">
    <Home/>
    <About/>
    <Education/>
    <Experience/>
    <Portfolio/>
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
    padding:10px
  }
</style>
