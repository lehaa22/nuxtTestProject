<!--Дань уважения прошлому-->
<template>
  <div class="jopa-nevidimka" @click="handler"></div>
</template>

<script>
export default {
  methods: {
    handler: function () {
      console.log('НЕ СМОТРИ СЮДА');
      alert('НЕ СМОТРИ СЮДА');
    }
  }
}
</script>

<style scoped>
.jopa-nevidimka {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 60px;
}
</style>
