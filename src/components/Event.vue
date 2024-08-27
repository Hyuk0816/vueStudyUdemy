<script>
  export default {
    name: 'EventComponent',
    props: {
      text: String,
    }
  }
</script>

<template>
  <div class="event">
    <p>
      {{text}}
    </p>
  </div>
</template>

<style >
  .event{
    background-color: #444;
    padding: 10px 20px;
    color: red;
    font-size: small;

  }
  .event p {
    margin: 0;
  }
</style>