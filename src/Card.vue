<template>
  <div v-for="(data, i) in post" :key="i">
    <img :src="data.image" alt="원룸" class="room-img" />
    <h4 @click="toggle(i)">{{ data.title }}</h4>
    <p>{{ data.price }}원</p>
  </div>
</template>

<script>
export default {
  name: 'CaRd',
  props: {
    post: Array,
    toggle: Function,
  },
};
</script>

<style></style>
