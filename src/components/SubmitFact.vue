<template>
    <div>
      <h1>Submit Your Cat Fact</h1>
      <div class="form-box">
        <FactForm @add-fact="addFact" />
      </div>
      <ul>
        <li v-for="fact in userFacts" :key="fact" class="submitted-fact">{{ fact }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  import FactForm from './FactForm.vue';
  
  export default {
    name: 'SubmitFact',
    components: {
      FactForm,
    },
    data() {
      return {
        userFacts: [],
      };
    },
    methods: {
      addFact(fact) {
        this.userFacts.push(fact);
      },
    },
  };
  </script>
  
  <style scoped>
  h1 {
    color: #ff69b4;
    margin-bottom: 20px;
  }
  
  .form-box {
    background-color: #ffe4e1;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
  }
  
  .submitted-fact {
    background-color: #fff0f5;
    padding: 10px;
    margin: 5px 0;
    border-radius: 8px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  }
  </style>
  