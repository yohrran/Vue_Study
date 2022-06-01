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
</template>

<script>
export default {
  name: 'MoDal',
  return() {},
};
</script>

<style></style>
