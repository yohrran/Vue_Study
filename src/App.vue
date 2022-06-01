<template>
  <div class="black-bg" v-if="modalState">
    <div class="white-bg">
      <h4>{{ post[clickData].title }}</h4>
      <h4>{{ post[clickData].content }}</h4>
      <img :src="post[clickData].image" alt="원룸" class="room-img" />
      <h4>{{ post[clickData].price }}원</h4>

      <button @click="toggle">닫기</button>
    </div>
  </div>

  <Discount />
  <div class="menu">
    <a v-for="(tag, i) in menu" :key="i">{{ tag }}</a>
  </div>

  <button @click="toggle">모달열기</button>
  <div v-for="(data, i) in post" :key="i">
    <img :src="data.image" alt="원룸" class="room-img" />
    <h4 @click="toggle(i)">{{ data.title }}</h4>
    <p>{{ data.price }}원</p>
  </div>
</template>

<script>
import post from './components/post.js';
import Discount from './Discount.vue';

export default {
  name: 'App',
  data() {
    return {
      clickData: 0,
      modalState: false,
      menu: ['Home', 'Shop', 'About'],
      products: ['역상돔 원룸', '천호동 원룸', '마포구 원룸'],
      money: [40, 70, 90],
      count: [0, 0, 0],
      post: post,
    };
  },
  methods: {
    increase(i) {
      this.count[i]++;
    },
    toggle(i) {
      this.modalState = !this.modalState;
      this.clickData = i;
    },
  },

  components: {
    Discount,
  },
};
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
  background: rgba(0, 0, 0, 0.5);
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
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
