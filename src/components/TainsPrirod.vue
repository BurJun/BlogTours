<template>
  <div class="new-block">
    <div class="circle-container">
      <div class="circle">
        <img src="@/components/img/image4.jpg" alt="Изображение 4">
      </div>
    </div>
    <div class="text-container">
      <h3>Тайны природы</h3>
      <p style="width: 300px;">На первый взгляд Швейцария выглядит страной, где природа и человек уживаются в идеальной гармонии. Но так ли это на взгляд второй и третий?</p>
      <my-button  @click="toggleDetails">Подробнее</my-button>
    </div>
    <div class="text-container dop" v-if="showDetails"  :class="{ 'show-details': showDetails }">
      <p>Заснеженные туманные Альпы, зеркальная лазурная гладь Женевского озера, бескрайние изумрудные лесные массивы, обрамляющие величественные берега, 
        пьянящий терпкой пронзительной свежестью воздух, от которого кружится голова, воинственные средневековые замки, 
        как стражи, возвышающиеся над городами и охраняющие их великую историю, 
        уплывающие в незыблемую даль бескрайние моря виноградников, бережно запрятанные в маленьких очаровательных деревушках, природа, вдохновляющая, манящая своей волшебной чистотой…</p>
    </div>
  </div>
</template>
<script>
import MyButton from "@/components/UI/MyButton.vue";
export default{
  name:'TainsPrirod',
  components: { MyButton, },
  data() {
    return {
      showDetails: false,
    };
  },
  methods: {
    toggleDetails() {
      this.showDetails = !this.showDetails;
    },
  },
}
</script>
<style scoped>
.new-block {
  position: relative;
  margin-top: 100px;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 20px;
}
.new-block::before,
.new-block::after {
  content: '';
  position: absolute;
  width: 600px;
  height: 600px;
  border-radius: 50%;
  background-color: #27ae60;
}

.new-block::before {
  top: 0px;
  left: 80px;
}

.new-block::after {
  bottom: 10px;
  right: 10px;
  width: 200px;
  height: 200px; 
}
.circle-container {
  display: flex;
  align-items: center; /* Добавлено для вертикального выравнивания по центру */
}

.circle {
  margin-top: 50px;
  border-radius: 50%;
  overflow: hidden;
  width: 500px;
  height: 500px; 
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1; 
}

.circle img {
  width: 100%; 
  height: 100%; 
  object-fit: cover;
}

.text-container {
  text-align: center;
}

h3 {
  font-size:40px;
  margin-bottom: 20px; /* Уменьшенный отступ снизу для близкого расположения блоков */
 
}
h3, p {
  position: relative; /* Устанавливаем для потенциального управления z-index */
  z-index: 2; /* Значение z-index для текста и кнопки, чтобы они находились перед .new-block::after */
}
.dop{
  width: 600px;
  height: 600px;
  border-radius: 50%;
  background-color: #27ae60;
  transition: opacity 5s; /* Устанавливаем время анимации */
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;

}
.dop p{
 width: 500px;
}
.show-details {
  opacity: 1; /* Показываем элемент с анимацией */
}
</style>