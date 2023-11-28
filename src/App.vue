<template>
  <div class="app">
    <from @submit.prevent>
      <h4>Создание поста</h4>
      <input v-bind:value="title" @input="title = $event.target.value" class="input" type = "text" placeholder="Название поста">
      <input v-bind:value="body" @input="body = $event.target.value" class="input" type = "text" placeholder="Описание поста">
      <button class="btn" @click="createPost">Создать пост</button>
    </from>
    <div class="post" v-for ="post in posts">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong>{{ post.body}}</div>
    </div>
  </div>
</template>

<script>

export default {
  data(){
    return {
      posts:[
        {id:1, title:'Javacript', body: 'Описание поста'},
      ],
      title: '',
      body: ''
    }
  },
  methods:{
    createPost(){
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = '';
      this.body = '';
    },
  }
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app{
  padding: 20px;
}

.post{
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

form{
  display: flex;
  flex-direction: column;
}

.input{
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn{
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
  align-self: flex-end;
}
</style>