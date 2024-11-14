<template>
    <div class="universe">
      <h3>{{ earthName }}</h3>
      <p>{{ getPeter(earthName) }}</p>
      <button @click="meetPeter">Let's Meet 🕷️</button>
      
      <!-- Slot for additional content (e.g., Gwen, Mary Jane) -->
      <div class="slot-content">
        <slot name="peter-img"></slot>
        <slot name="mj"></slot>
      </div>
    </div>
  </template>
  
  <script>
  import API from '@/modules/multiverse/index';
  
  export default {
    name: 'SpidyVerse',
    props: {
      earthName: {
        type: String,
        required: true,
      },
    },
    methods: {
      getPeter(earth) {
        return API.EARTH[earth] || 'Unknown Spider-Man';
      },
      meetPeter() {
        this.$emit('show-meme');
      },
    },
  };
  </script>
  
  <style scoped>
  .universe {
    background-color: #f5f5f5;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    margin: 20px auto;
    text-align: center;
    width: 70%;
  }
  button {
    margin-top: 10px;
    background-color: #e63946;
    color: white;
    border: none;
    padding: 8px 16px;
    cursor: pointer;
    border-radius: 5px;
  }
  button:hover {
    background-color: #d62828;
  }
  .slot-content {
    margin-top: 15px;
    font-style: italic;
    color: #555;
  }
  </style>
  