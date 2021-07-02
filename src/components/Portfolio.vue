<template>  
  <section class="section" id="portfolio">
    <div class="titleContainer">
      <span class="dots"></span>
      <h3 class="titles">{{title}}</h3>
    </div>
    <div class="portfoArea">
      
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return{
      title:'Portfolio',
    }
  },
  methods: {

  },
}
</script>

<style>
  .portfoArea{
    margin-top: 20px;
    padding: 20px;
    width: 90%;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #189fb149;
  }
  
</style>