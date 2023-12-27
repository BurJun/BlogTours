<template>
  <footer class="footer">
    <div class="footer-content">
      <h1 class="brand">CoryJoy</h1>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
};
</script>

<style scoped>
.footer {
  background-color: #27ae60; /* Цвет фона подвала */
  color: white; /* Цвет текста подвала */
  padding: 20px;
  text-align: center;
}

.footer-content {
  display: flex;
  align-items: center;
  justify-content: center;
}

.brand {
  font-size: 24px;
}

</style>