<template>
    <form @submit.prevent="submitFact">
      <div class="input-group">
        <label for="fact">Submit a Cat Fact:</label>
        <input v-model="newFact" id="fact" required />
      </div>
      <button type="submit">Submit</button>
    </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newFact: '',
      };
    },
    methods: {
      submitFact() {
        this.$emit('add-fact', this.newFact);
        this.newFact = '';
      },
    },
  };
  </script>
  
  <style scoped>
  .input-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
    color: #ff69b4;
    font-weight: bold;
  }
  
  input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ffb6c1;
    border-radius: 8px;
    background-color: #fff0f5;
    box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
  }
  
  button {
    background-color: #ffd1dc;
    border: none;
    color: #4a4a4a;
    padding: 10px 20px;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  button:hover {
    background-color: #ffc0cb;
  }
  </style>
  