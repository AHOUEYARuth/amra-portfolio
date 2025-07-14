<script setup>
import PortfolioPage from './components/PortfolioPage.vue';
</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header> -->

  <!-- <main> -->
    <div class="app">
       <PortfolioPage/>
    </div>
    
    <!-- <TheWelcome /> -->
  <!-- </main> -->
</template>

<style>
.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
  padding: 0;
  justify-content: center;
  align-items: center;
  background-color: #2c3e50;
}
</style>
