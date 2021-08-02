<template>
  <header>
    <h1 class="red">{{head}} <sub class="red">{{hash}}</sub></h1>
    <div class="aside">
      <ul>
        <li 
          class="navItem"
          v-for="item in navItem" 
          :key="item.id"
        >
        <a :href="item.link">
          <img class="navIcon" :src="item.icon">
          {{item.name}}
        </a>
        </li>
      </ul>
    </div>
    <div class="company">
      {{company}}
    </div>
  </header>
</template>

<script>
export default {
  data(){
    return{
      head:'RED',
      hash:'#',
      navItem: [
        {name:'Home',icon: require('../assets/icon/home.svg'),link:'#home'},
        {name:'About',icon: require('../assets/icon/avatar.svg'),link:'#about'},
        {name:'Eduction',icon: require('../assets/icon/education.svg'),link:'#education'},
        {name:'Experience',icon: require('../assets/icon/experience.svg'),link:'#experience'},
        {name:'Portfolio',icon: require('../assets/icon/file.svg'),link:'#portfolio'},
      ],
      company: '© 2021 NomNom.'
    }
  }
}
</script>

<style>
  header{
    width: var(--asidewidth);
    margin: 0;
    position: fixed;
  }
  .red{
    color: #b30f0f;
  }
  h1{
    padding: 20px;
    padding-bottom: 0;
    text-align: center;
    font-size: 38px;
  }
  sub{
    color: #ffffff;
  }
  /* nav */
  .navItem{
    margin: 40px;
    font-size: 28px;
    margin-left: 30px;
  }
  .navItem a{
    transition: all .5s;
  }
  .navItem a:hover{
    color: #b30f0f;
  }
  .navIcon{
    width: 30px;
    height: 30px;
    margin-right: 15px;
    vertical-align: bottom;
  }
  .company{
    color: #a7a7a7;
    font-size: 14px;
    text-align: center;
  }
  /* section */
  .titleContainer{
    display: flex;
    position: relative;
    justify-content: start;
    width: 100%;
  }
  .dots{
    background-image: url(../assets/icon/dotsmenu.svg);
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    position: absolute;
    width: 50px;
    height: 50px;
    opacity: .3;
    top: -25px;
  }
  .titles{
    margin: 0;
    margin-left: 10px;
    color: chocolate;
    align-self: flex-start;
    font-size: 48px;
    z-index: 1;
  }
  .section{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>