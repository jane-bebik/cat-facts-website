<template>
  <div id="app">
    <nav class="nav">
      <button @click="currentView = 'home'" :class="{'active': currentView === 'home'}">Home</button>
      <button @click="currentView = 'submit'" :class="{'active': currentView === 'submit'}">Submit a Fact</button>
    </nav>

    <div class="content-box">
      <HomeView v-if="currentView === 'home'" />
      <SubmitFact v-if="currentView === 'submit'" />
    </div>
  </div>
</template>

<script>
import HomeView from './components/HomeView.vue';
import SubmitFact from './components/SubmitFact.vue';

export default {
  components: {
    HomeView,
    SubmitFact,
  },
  data() {
    return {
      currentView: 'home',
    };
  },
};
</script>

<style scoped>
body {
  font-family: 'Arial', sans-serif;
  background-color: #f8e7e9; /* Pastel pink background */
  color: #4a4a4a;
  margin: 0;
  padding: 0;
}

#app {
  text-align: center;
  padding: 20px;
}

.nav {
  margin-bottom: 20px;
}

.nav button {
  background-color: #ffd1dc; /* Light pastel pink */
  border: none;
  color: #4a4a4a;
  padding: 10px 20px;
  margin: 0 10px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.nav button:hover {
  background-color: #ffc0cb; /* Slightly darker pink on hover */
}

.nav button.active {
  background-color: #ffb6c1; /* Active button color */
}

.content-box {
  background-color: #ffffff; /* White background for the content box */
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 0 auto;
}
</style>
