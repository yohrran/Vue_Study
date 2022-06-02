<template>
  <div class="black-bg" v-if="modalState">
    <div class="white-bg">
      <h4>{{ post[clickData].title }}</h4>
      <h4>{{ post[clickData].content }}</h4>
      <img :src="post[clickData].image" alt="원룸" class="room-img" />
      <input v-model.number="month" placeholder="수량 입력해주세요" />
      <input type="range" v-model.number="value" />
      <p>{{ value }}</p>
      <h4>{{ post[clickData].price }}원</h4>
      <p>{{ month * post[clickData].price }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MoDal',
  data() {
    return {
      month: '',
      value: '',
    };
  },
  watch: {
    month(a) {
      if (typeof a !== 'number') {
        alert('숫자만 입력해주세요');
      }
    },
  },
  beforeUpdate() {
    if (this.month === 2) {
      alert('에러');
      this.month = 0;
    }
  },
  props: {
    post: Object,
    clickData: Number,
    modalState: Boolean,
  },
};
</script>

<style></style>
