<template>  
  <section class="about">
    <div>About Me</div>
    <h1>About Me</h1>
    <span>All of about me</span>
    <ul>
      <li>kerker</li>
    </ul>
    <button>More about me</button>
    <div class="scroll-down">
      <a href="#"></a>
    </div>
  </section>
</template>

<script>
export default {
  name:'Section2',
  data(){
    return{
      head:'Cat',
      hash:'#',
    }
  }
}
</script>

<style>
  h1{
    margin: 0;
    color: white;
  }
  .about{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>