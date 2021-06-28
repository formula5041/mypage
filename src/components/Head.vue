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
        <img class="navIcon" :src="item.icon">
        {{item.name}}
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name:'Head',
  data(){
    return{
      head:'JIBAN',
      hash:'#',
      navItem: [
        {name:'Home',icon: require('../assets/icon/home.svg'),link:''},
        {name:'About',icon: require('../assets/icon/avatar.svg'),link:''},
        {name:'Eduction',icon: require('../assets/icon/education.svg'),link:''},
        {name:'Experience',icon: require('../assets/icon/experience.svg'),link:''},
        {name:'Portfolio',icon: require('../assets/icon/home.svg'),link:''},
        {name:'LearningStyle',icon: require('../assets/icon/home.svg'),link:''},
      ],
    }
  }
}
</script>

<style>
  header{
    width: var(--asidewidth);
    height: 800px;
    border: 1px solid #ffffff;
    margin: 0;
    position: fixed;
  }
  h1{
    padding: 10px;
    text-align: center;
    color: white;
  }
  sub{
    color: #2951af;
  }
  .navItem{
    margin: 30px;
    cursor: pointer;
  }
  .navIcon{
    width: 20px;
    height: 20px;
  }
</style>