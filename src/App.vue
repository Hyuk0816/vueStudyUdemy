<script >
  import data from './assets/movies.js';
  import Navbar from "./components/Navbar.vue";
  import Modal from "./components/Modal.vue";
  import Event from "./components/Event.vue";
  import Movie from "./components/Movies.vue";
  import SearchBar from "./components/SearchBar.vue";
  export default {
    name: 'App',
    methods:{
      increaseLikes(i){
        this.data[i].like +=1;
      }
    },

    data(){
      return {
        isModal: false,
        data:data,
        selectedMovie : 0,
        text:"Netfilx Demo Test"
      }
    },
    components:{
      Navbar: Navbar,
      Modal: Modal,
      Event: Event,
      Movie: Movie,
      SearchBar: SearchBar,
    }

  }

</script>

<template>
  <Navbar/>
  <Event :text = "text" />
  <SearchBar />
  <Movie
      :data="data"
      @openModal="isModal = true; selectedMovie=$event"
      @increaseLikes="increaseLikes"/>
  <Modal
      :data="data"
      :isModal="isModal"
      :selectedMovie="selectedMovie"
      @closeModal="isModal=false"
    />
</template>

<style >
  .bg-yellow{
    background-color: gold;
  }
  * {
    box-sizing: border-box;
    margin: 0;
  }

  body {
    max-width: 768px;
    margin: 0 auto;
    padding: 20px;
  }

  h1,
  h2,
  h3 {
    margin-bottom: 1rem;
  }

  p {
    margin-bottom: 0.5rem;
  }

  button {
    margin-right: 10px;
    margin-top: 1rem;

  }

  .item {
    width: 100%;
    border: 1px solid #ccc;
    display: flex;
    margin-bottom: 20px;
    padding: 1rem;
  }

  .item figure {
    width: 30%;
    margin-right: 1rem;
  }

  .item img {
    width: 100%;
  }

  .item .info {
    width: 100%;
    text-align: left;
  }

  .modal {
    background: rgba(0, 0, 0, 0.7);
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal .inner {
    background: #fff;
    width: 80%;
    padding: 20px;
    border-radius: 10px;
    color: black;
  }
  .navbar{
    background: #000;
    padding: 20px;

  }
</style>
