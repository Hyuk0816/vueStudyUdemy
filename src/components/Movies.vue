<script>
  export default {
    name: 'MoviesComponent',
    props: {
      data: Array,
    }
  }
</script>

<template>
  <h1>영화정보</h1>
    <div class="container">
      <div v-for="(movie, i) in data" :key="i" class="item">
        <figure>
          <img :src="`${movie.imgUrl}`" :alt="movie.title">
        </figure>
        <div class="info">
          <h3 class="bg-yellow" :style="movie.textColor">
            {{movie.title}}
          </h3>
          <p>개봉: {{movie.year}} </p>
          <P>장르: {{movie.category}}</P>
          <button @:click="$emit('increaseLikes', i)">좋아요</button>
          <span>{{movie.like}}</span>
          <p>
            <button @:click="$emit('openModal', i)">상세보기</button>
          </p>
        </div>
      </div>
    </div>
</template>

<style>
  .container {
    padding: 20px;
  }
</style>