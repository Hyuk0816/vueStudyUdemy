
<template>
  <div class="search-box">
    <input type="search"
           v-model="inputText"
           placeholder="검색어 입력"
    >
    <button>검색</button>
  </div>
  <p>{{inputText}}</p>
</template>

<script >
export default {
  name: "SearchBarComponent",
  data(){
    return {
      inputText: '',
    }
  },
  watch:{
    inputText(name){
      //입력한 영화 제목이 데이터에 있는지 확이하는 일

    }
  }
}
</script>

<style>
  .search-box{
    padding: 10px;
    display: flex;
    justify-content: center;
  }

  .search-box input{
    padding: 5px 10px;
  }

  .search-box button{
    margin: 0 0 0 10px;
  }
</style>