
<template>
  <from @submit.prevent>
      <h3>Создание комментария</h3>
      <input v-model="post.title" class="input" type = "text" placeholder="Название поста">
      <input v-model="post.body" class="input" type = "text" placeholder="Описание поста">
      <my-button @click="createPost" style="margin-top: 15px;">Создать пост</my-button>
    </from>
</template>

<script>

import MyButton from "@/components/UI/MyButton.vue";
 export default{
  components:{MyButton},
    data(){
      return{
        post:{
          title: '',
          body: ''
        }
      }
    },
    methods:{
      createPost(){
      this.post.id = Date.now();
      this.$emit('create', this.post);
      this.post = {
        title: '',
        body: ''
      }
      }
    }
 }
</script>

<style scoped>
form{
  display: flex;
  flex-direction: column;
}

.input{
  width: 90%;
  border: 1px solid #27ae60;
  padding: 10px 15px;
  margin-top: 15px;
}

</style>