<template>


  <link rel="stylesheet" href="css/reset.css" >
  <link rel="stylesheet" href="css/index.css" >
  <link rel="stylesheet" href="css/header.css" >
  <link rel="stylesheet" href="css/footer.css" >

  

  <div class="menu" id="menu" @click="menuShow = true">
    <span></span>
    <span></span>
    <span></span>
  </div>
  <div class="menu-box" id="menuBtn">menu</div>
  <header>
    <nav>
      <div class="pcg-logo"></div>
      <h3 class="myName toSection" v-on:click="goSection" data-target="intro">CHEONGYEONG</h3>
    </nav>
  </header>

  <main class="index-page" id="app">
   <div class="menu-bgBlack" v-if="menuShow == true">
      <div class="closeBox" @click="menuShow = false">
         <h4>close</h4>
          <img src="img/close.png" alt="">
      </div>
      <div class="showMenu">
       <h1 v-on:click="goSection" data-target="about" class="toSection" @click="menuShow = false">about me</h1>
       <h1 v-on:click="goSection" data-target="project" class="toSection" @click="menuShow = false">project</h1>
       <h1 v-on:click="goSection" data-target="webclone" class="toSection" @click="menuShow = false">web clone</h1>
       <h1 v-on:click="goSection" data-target="contact" class="toSection" @click="menuShow = false">contact</h1>
      </div>
    </div>



   <intro />
   <about />
   <project />
   <webClawling />
   <clawlingSlide />
   <contact />

  <footer>
    <div class="pcg-logoWrap">
      <div class="footer-circle">

        <img src="img/logo-white.png" alt="">
     </div>
    </div>
  </footer>
  

</main>


<span></span>

  

</template>

<script>
import intro from './components/intro.vue';
import about from './components/about.vue';
import project from './components/project.vue';
import webClawling from './components/webClawling.vue';
import contact from './components/contact.vue';
import AOS from 'aos';




export default {
  name: 'App',
  components: {
    intro,about,project, webClawling, contact,
    },
    
    created() {
    AOS.init()
  },

   
  data() {
    return {
      menuShow : false,
      btnShow : false,
      scrollTop: 0,
    }
  },
  


  methods: {
    goSection(e) {
      e.preventDefault();
      if (!e.target.matches('.toSection')) {
        return;
      }
      const clickNav = document.getElementById(e.target.dataset.target);
      if (clickNav) {
        clickNav.scrollIntoView({ behavior: 'smooth' });
      }
    },

  },
 
}






</script>




<style scoped>



</style>
