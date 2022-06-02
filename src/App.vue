<template>
  <Discount />
  <transition name="fade">
    <Modal
      :post="post"
      :clickData="clickData"
      :modalState="modalState"
      @closeModal="modalState = false"
    />
  </transition>
  <div class="menu">
    <a v-for="(tag, i) in menu" :key="i">{{ tag }}</a>
  </div>

  <button @click="priceSort">가격 순 정렬 버튼</button>
  <button @click="priceBack">되돌리기</button>

  <Card :post="post" :toggle="toggle" />
</template>

<script>
import post from './components/post.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data() {
    return {
      clickData: 1,
      modalState: false,
      menu: ['Home', 'Shop', 'About'],
      products: ['역상돔 원룸', '천호동 원룸', '마포구 원룸'],
      money: [40, 70, 90],
      count: [0, 0, 0],
      post: post,
      origin: [...post],
    };
  },
  methods: {
    increase(i) {
      this.count[i]++;
    },
    toggle(i) {
      this.clickData = i;
      this.modalState = !this.modalState;
    },
    priceSort() {
      this.post.sort((a, b) => a.price - b.price);
    },
    priceBack() {
      this.post = [...this.origin];
    },
  },

  components: {
    Discount,
    Modal,
    Card,
  },
};
</script>

<style>
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  opacity: 1;
}

.fade-enter-from {
  transform: translateY(-1000px);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY(0px);
}

.start {
  opacity: 0;
  transition: all 1s;
}
.end {
  opacity: 1;
}
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
