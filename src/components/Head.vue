<template>
  <header>
    <h1>{{head}} <sub>{{hash}}</sub></h1>
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
  name:'Head',
  data(){
    return{
      head:'NOM',
      hash:'#',
      navItem: [
        {name:'Home',icon: require('../assets/icon/home.svg'),link:'#home'},
        {name:'About',icon: require('../assets/icon/avatar.svg'),link:'#about'},
        {name:'Eduction',icon: require('../assets/icon/education.svg'),link:''},
        {name:'Experience',icon: require('../assets/icon/experience.svg'),link:''},
        {name:'Portfolio',icon: require('../assets/icon/file.svg'),link:''},
        {name:'LearningStyle',icon: require('../assets/icon/study.svg'),link:''},
      ],
      company: '© 2021 NomNom.'
    }
  }
}
</script>

<style>
  header{
    width: var(--asidewidth);
    /* border: 1px solid #ffffff; */
    margin: 0;
    position: fixed;
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
    color: #e00101;
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
  /* @media (max-width:1280px) {
     .navItem{
      margin: 30px;
      font-size: 12px;
    }
    .navIcon{
      width: 20px;
      height: 20px;
      margin-right: 10px;
      vertical-align: bottom;
    }
    .company{
      color: #a7a7a7;
      font-size: 12px;
      text-align: center;
    }
  } */
</style>