<template>
  <div class="post">
    <div>
      <div><strong>От:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong>{{ post.body }}</div>
    </div>
    <div class="post_btns">
      <span class="like-span">{{ likesCount }}</span>
      <my-button @click="incrementLikes">
        <font-awesome-icon icon="heart"></font-awesome-icon>
      </my-button>
      <!-- my-button для удаления -->
      <my-button @click="$emit('remove', post)">Удалить</my-button>
    </div>
  </div> 
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
import { library } from "@fortawesome/fontawesome-svg-core";
import { fas } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(fas);

export default {
  components: { MyButton, FontAwesomeIcon },
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      likesCount: 0,
    };
  },
  methods: {
    incrementLikes() {
      this.likesCount++;
    },
  },
};
</script>

<style scoped>
.post{
  padding: 15px;
  border: 2px solid #27ae60;
  margin-top: 15px;

  display: flex;
  align-items: center;
  justify-content: space-between;
}
.like-span{
 margin-right: 10px;
 color: #27ae60;
}

</style>