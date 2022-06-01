<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div>
    <h4>{{ products[0] }}원룸</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }}원룸</h4>
    <p>70 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}원룸</h4>
    <p>90 만원</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      products: ['역상돔 원룸', '천호동 원룸', '마포구 원룸'],
    };
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
