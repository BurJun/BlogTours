
<template>
  <div class="menu">
    <h1 class="name-sait">CozyJoy</h1>
    <div class="but_m">
      <button class="tours-menu" @click="navigate('home')">Главная</button>
      <button  @click="navigate('contacts')">Контакты</button>
      <my-button>Записаться</my-button>
    </div>
    
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
  components:{
    MyButton,
  },
  methods: {
    navigate(view) {
      this.$emit('navigate', view);
    },
  },
};
</script>
<style>
.menu {

  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0;
  background-color: rgba(240, 240, 240, 0.7); 
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
}

.name-sait{
  font-size: 'Montserrat', Arial, sans-serif;
  margin-left: 100px;
}
.but_m{
  margin-right: 40px;
}
.menu button {
  border: none; 
  background: none; 
  margin: 0; 
  padding: 40px 40px; 
  cursor: pointer;
  font-size: 18px;
  font-family: Bradley Hand, cursive;
}
.tours-menu{
  background-color: #ffcc00; 
  color: #000000; 
  font-weight: bold; 
}

.menu button:hover {
  text-decoration: underline; 
}
</style>