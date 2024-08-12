<template>
    <div>
      <h1>Random Cat Facts</h1>
      <div v-for="fact in catFacts" :key="fact" class="fact-box">
        <CatFact :fact="fact" />
      </div>
      <button @click="fetchCatFacts">Load New Facts</button>
    </div>
  </template>
  
  <script>
  import CatFact from './CatFact.vue';
  
  export default {
    name: 'HomeView',
    components: {
      CatFact,
    },
    data() {
      return {
        catFacts: [],
      };
    },
    methods: {
      fetchCatFacts() {
        this.catFacts = [
          'Cats have five toes on their front paws but only four toes on their back paws.',
          'A group of cats is called a clowder.',
          'Cats can rotate their ears 180 degrees.',
          'The average cat sleeps for 13 to 16 hours a day.',
        ];
      },
    },
    created() {
      this.fetchCatFacts();
    },
  };
  </script>
  
  <style scoped>
  h1 {
    color: #ff69b4; /* Pink color for the header */
    margin-bottom: 20px;
    font-family: 'Georgia', serif;
  }
  
  .fact-box {
    background-color: #ffe4e1; /* Light pink background */
    padding: 15px;
    margin: 10px 0;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  button {
    background-color: #ffd1dc;
    border: none;
    color: #4a4a4a;
    padding: 10px 20px;
    margin-top: 20px;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  button:hover {
    background-color: #ffc0cb;
  }
  </style>
  