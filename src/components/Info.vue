<template>
  <div class="inform">
    <h2>Последние новости путешествия</h2>
    <div class="info-container">
      <div class="info-block">
        <img src="@/components/img/image2.jpg" alt="Изображение 1">
        <p>Текст для блока 1</p>
      </div>
      <div class="info-block">
        <img src="@/components/img/image3.jpg" alt="Изображение 2">
        <p>Текст для блока 2</p>
      </div>
      <div class="info-block">
        <img src="@/components/img/image4.jpg" alt="Изображение 3">
        <p>Текст для блока 3</p>
      </div>
    </div>
  </div>
</template>
<script>
export default{
  name:'info'
}
</script>
<style scoped>
.inform {
  text-align: center;
  padding: 20px;
}

h2 {
  font-size: 40px;
  font-weight: 900;
  margin-bottom: 20px;
  margin-top: 80px;
}

.info-container {
  display: flex;
  justify-content: space-around;
  margin-top: 30px;
}

.info-block {
  width: 30%; 
  background-color: #27ae60;/* Задайте ширину блока по вашему усмотрению */
}

.info-block img {
  width: 100%;
  max-width: 100%; /* Укажите максимальную ширину изображения по вашему усмотрению */
  height: auto;
  margin-bottom: 10px;
}

.info-block p {
  font-size: 16px;
  color: white;
}
</style>