<script>
  export default {
    name: 'EventComponent',
    props: {
      text: String,
      isEventOpen: Boolean,
    },
    data(){
      return {
        isOpen: true,
      }
    }
  }
</script>

<template>
  <div class="event" :class="{show: isOpen}">
    <p>
      {{text}}
    </p>
    <button @click="isOpen=false">X</button>
  </div>
</template>

<style >
  .event{
    background-color: #444;
    padding: 10px 20px;
    color: red;
    font-size: small;
    text-align: center;
    display: flex;
    justify-content: space-between;
    align-items: center;
    display: none;
  }
  .show {
    display: flex;
  }
  .event p {
    margin: 0;
  }
  .event button{
    margin: 0;
  }
</style>