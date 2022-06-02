<template>
  <div>
    <h4 class="discount">지금 결제하면 {{ salesNumber }}% 할인</h4>
  </div>
</template>

<script>
export default {
  name: 'DisCount',
  data() {
    return {
      salesNumber: 30,
    };
  },
  mounted() {
    setInterval(() => {
      this.salesNumber--;
    }, 1000);
  },
};
</script>

<style>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>
