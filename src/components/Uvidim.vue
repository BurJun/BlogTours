
<template>
  <div class="sightseeing-block">
    <h3>Какие места вы увидите</h3>
    <div class="circles-container">
      <div class="info-circle">
        <!-- Перечислите здесь информацию для правого круга -->
        <ul>
          <li>KKL концертный зал и музей современного искусства</li>
          <li>Уникальные деревянные мосты украшенные картинами</li>
          <li>Рыцарский дворец</li>
          <li> Расписные дома и площади</li>
          <li>Церковь Иезутов, где хранится облачение св. покровителя Швейцарии</li>
          <li>Набережную с которой открываются виды на горы или поднимемся на смотровую площадку</li>
          <li>Хофкирхе с которой связана одна из легенд о возникновении города</li>
          <li>Памятник умирающему Льву</li>
        </ul>
      </div>
      <div class="image-circle" @click="toggleImage">
        <img :src="currentImage" alt="Изображение" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SightseeingBlock',
  data() {
    return {
      currentImage: require("@/components/img/image5.jpg"),
      alternateImage: require("@/components/img/image6.jpg"), // Path to the alternative image
      isAlternateImage: false,
    };
  },
  methods: {
    toggleImage() {
      this.isAlternateImage = !this.isAlternateImage;
      this.currentImage = this.isAlternateImage
        ? this.alternateImage
        : require("@/components/img/image8.jpg");
    },
  },
};
</script>

<style scoped>
.sightseeing-block {
  text-align: center;
}

h3 {
  margin-top: 100px;
  font-size: 40px;
  margin-bottom: 20px;
}

.circles-container {
  margin-top: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.info-circle {
  margin-left: 50px;
  width: 45%;
  height: 600px; 
  border-radius: 50%;
  overflow: hidden;
  background-color: #27ae60;
}

.image-circle {
  width: 45%; 
  height: 600px;
  border-radius: 50%;
  overflow: hidden;
}

.info-circle ul {
  padding: 0;
  text-align: left;
  margin-left: 100px;
  margin-top: 150px;
}

.info-circle li {
  margin-bottom: 10px;
  color: white;
}
.image-circle {
  margin-left: 50px;
  width: 45%;
  height: 600px; 
  border-radius: 50%;
  overflow: hidden;
}

.image-circle img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>