<template>
  <div id="app">
    <div class="black-bg" v-if="isOpenedModal">
      <div class="white-bg">
        <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
        <button @click="isOpenedModal = !isOpenedModal">닫기</button>
      </div>
    </div>

    <div class="menu">
      <a v-for="list in menu" :key="list">{{ list }}</a>
    </div>

    <div 
      v-for="room in rooms" 
      :key="room.id" 
    >
      <img :src="room.image" class="room-img"/>
      <h4>{{ room.title }}</h4>
      <p>{{ room.price }}</p>
      <p>{{ room.content }}</p>
    </div>
  </div>
</template>

<script>
import data from './data/post';

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      rooms: data,
      isOpenedModal: false,
      cnt1: 0,
      cnt2: 0,
      cnt3: 0,
      menu: ['Home', 'Shop', 'About'],
      product: ['역삼동원룸', '천호동원룸', '마포구원룸'],

    }
  },
  methods: {

  },
}
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
