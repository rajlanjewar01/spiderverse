<template>
    <div class="multiverse">
      <h2>🕸️ Welcome to the Spider-Verse!</h2>
      
        <!-- Meme section that shows up on button click -->
      <div v-if="showMeme" class="meme-container">
        <img src="../assets/spider-verse/animated-gif-finger-pointing-meme.gif" alt="Spider-Man Meme" class="meme-img" />
      </div>

      <div class="spiderman-space">
        <!-- Universe for Earth 616 with Gwen Stacy -->
        <spidyverse earthName="EARTH_616" @show-meme="toggleMeme">
            <template #peter-img>
              <img src='../assets/spider-verse/peter1-tom-holland.jpg' class='img-fluid'>
            </template>
            <template #mj>
              💖 MJ is here to support Peter-1!
            </template>
        </spidyverse>
        
        <!-- Universe for Earth 96283 with Mary Jane -->
        <spidyverse earthName="EARTH_96283" @show-meme="toggleMeme">
            <template #peter-img>
              <img src='../assets/spider-verse/peter-2-tobey-maguire.jpg' class='img-fluid'>
            </template>
            <template #mj>
            💖 Mary Jane Watson is rooting for Peter-2!
            </template>
        </spidyverse>
        
        <!-- Universe for Earth 120703 with no extra character -->
        <spidyverse earthName="EARTH_120703" @show-meme="toggleMeme">
            <template #peter-img>
              <img src='../assets/spider-verse/peter3-andrew-garfield.jpg' class='img-fluid'>
            </template>
            <template #mj>
              💖 Gwen Stacy is here to support Peter-1!
            </template>
        </spidyverse>
      </div>
    </div>
  </template>
  
  <script>
  import spidyverse from '@/components/SpidyVerse.vue';
  import API from '@/modules/multiverse/index';
  
  export default {
    name: 'MultiVerse',
    components: { spidyverse },
    data() {
      return {
        showMeme: false,
        earths: Object.keys(API.EARTH),
      };
    },
    methods: {
      toggleMeme() {
        this.showMeme = true;
        setTimeout(() => {
          this.showMeme = false;
        }, 5000);
      },
    },
  };
  </script>
  
  <style scoped>
  .spiderman-space {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 10px;
  }
  .multiverse {
    text-align: center;
    padding: 30px;
  }
  .meme-container {
    margin-top: 20px;
    animation: fade-in 0.5s ease-out;
  }
  .meme-img {
    width: 350px;
    height: auto;
  }
  .img-fluid {
    width: 100%;
    height: auto;
  }
  @keyframes fade-in {
    from { opacity: 0; }
    to { opacity: 1; }
  }
  </style>
  