
<template>
  <div class="tour-info">
    <h3>Информация тура</h3>
    <div class="info-row">
      <div class="info-block" v-for="(info, icon) in tourInfo" :key="icon">
        <font-awesome-icon :icon="['fas', icon]"  style="color: #27ae60"/>
        <p>{{ info }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faWalking, faClock, faMobile, faTimes, faLanguage, faChild } from '@fortawesome/free-solid-svg-icons';

export default {
  name: 'TourInfo',
  components: { FontAwesomeIcon },
  data() {
    return {
      tourInfo: {
        walking: 'Индивидуальная, пешеходная',
        clock: '1 час 30 минут',
        mobile: 'Билет в телефоне',
        times: 'Бесплатная отмена',
        language: 'Русский язык',
        child: 'Можно с детьми',
      },
    };
  },
};
</script>

<style scoped>
.tour-info {
  text-align: center;
}

h3 {
  margin-top: 100px;
  font-size: 24px;
  margin-bottom: 20px;
}

.info-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* Три столбца с одинаковой шириной */
  gap: 10px; /* Расстояние между блоками */
  padding: 20px 300px;
}

.info-block {
  text-align: center;
  margin: 0;
}

p {
  margin-top: 5px;
  font-size: 16px;
}
</style>