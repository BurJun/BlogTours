<template>
  <Menu @navigate="navigate" style="z-index: 1;"></Menu>
  <div class="osnova">
      <div class="oval">
        <img src="@/components/img/image1.png" alt="Изображение" />
        <div class="overlay-text">
          <div class="text">Незабываемое путешествие</div>
          <div class="text below">в Швейцарию</div>
        </div>
      </div>
  </div>
  
  <TourInfo></TourInfo>
  <TainsPrirod></TainsPrirod>
  <SightseeingBlock></SightseeingBlock>
  <Info></Info>
  <Start></Start>
  <div class="app">
    <h3 style="margin-top: 20px; font-size: 40px;">Отзывы туристов</h3>  
    <my-button @click="showDialod" style="margin-top: 20px;">Создать отзыв</my-button>
      <my-dialog v-model:show="dialogVisibole" >
        <post-form @create="createPost"/>
      </my-dialog>
      
      <post-list v-bind:posts="posts" @remove="removePost"/>
  </div>
  <Footer></Footer>
</template>

<script>
import Menu from "@/components/Menu.vue";
import Start from "@/components/Start.vue";
import Info from "@/components/Info.vue";
import SightseeingBlock from "@/components/Uvidim.vue";
import TourInfo from "@/components/InfoTur.vue";
import TainsPrirod from "@/components/TainsPrirod.vue";
import Footer from "@/components/Footer.vue";
import MyButton from "@/components/UI/MyButton.vue";
import MyDialog from "./components/UI/MyDialog.vue";
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
export default {
  name: 'App',
  components:{
    PostList, PostForm,MyDialog,MyButton,Menu,Info,TainsPrirod,Start,TourInfo,SightseeingBlock,Footer,
  },
  data(){
    return {
      posts:[
        {id:1, title:'Javacript', body: 'Описание поста'},
        {id:2, title:'Javacript', body: 'Описание поста'},
        {id:3, title:'Javacript', body: 'Описание поста'},
        {id:4, title:'Javacript', body: 'Описание поста'},
      ],
      dialogVisibole: false,

    }
  },
  methods:{
    createPost(post){
      this.posts.push(post);
      this.dialogVisibole = false;
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialod(){
      this.dialogVisibole = true;
    },
    
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Bradley Hand, cursive;
}

.app {
  padding: 60px;
}

.osnova {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.oval {
  margin-top: 50px;
  position: relative;
  width: 1400px; 
  height: 700px; 
  border-radius: 50%;
  overflow: hidden;
}

.text {
  font-size: 60px;
  font-weight: 900;
  color: black; 
  position: absolute;
  top: 30%;
  left: 45%;
  transform: translate(-50%, -50%);
  z-index: 1; 
  
}

.oval img {
  width: 100%; 
  height: 100%; 
  object-fit: cover;
}
.below{
  background-color: rgba(240, 240, 240, 0.7); 
  margin-top: 200px;
  margin-left: 200px;
  padding: 30px;
  border-radius: 30px;
}
</style>