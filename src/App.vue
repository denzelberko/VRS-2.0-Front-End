<template>

  <div>
    
    <router-view/>

  </div>

  
  </template>
 
  <script>
  import ModalRoot from '@/Modal/ModalRoot.vue';
  import ModalService from '@/Modal/Modalservice';
  import TestModal from '@/Modal/TestModal.vue';
  import AdminPage from './components/AdminPage.vue';
  import SearchTrips from './components/SearchTrips.vue';

  
  export default{
      name: "App",
      components: { ModalRoot, AdminPage, SearchTrips},
      methods: {
        addModal() {
          ModalService.open(TestModal);
        }
      }
  
  }
  </script>

  
  <style>
   .nav a{
      background-color: #0D0047;
      overflow: hidden;
   }
   .nav c{
      background-color: #0D0047;
      overflow: hidden;
   }
   .nav c {
      color: #f2f2f2f2;
      padding: 20px 30px;
      text-align: center;
      text-decoration: none;
      font-size: 20px;
      font-weight: bold;
  }
   .nav a {
      color: #f2f2f2f2;
      padding: 20px 109.1px;
      text-align: center;
      text-decoration: none;
      font-size: 20px;
  }
  .nav a:hover{
      background-color:#ddd;
      color: #000160;
  }
  body, html {
  padding: 0;
  margin: 0;
  width: 100%;
  min-height: 100vh;
  }
  body {
  background-color: #f2f2f2f2;
  }
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
  </style>
  

