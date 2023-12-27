
<template>
  <div class="start-journey">
    <h3 style="margin-top: 100px;">Если в вашем списке есть Швейцария, то</h3><h1 style="margin-bottom: 40px;">Ваше путешествие начинается здесь...</h1>
    <my-button style="margin-top: 20px;">Записаться</my-button>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
  name: 'Start',
  components: { MyButton, },
};
</script>

<style scoped>
.start-journey {
  
  text-align: center;
  margin-top: 50px;
}

h3 {
  font-size: 24px;
}
</style>