<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default{
  name:'my-button'
}
</script>

<style scoped>
.btn{
  padding: 10px 15px;
  background: none;
  color: #27ae60;
  border: 1px solid #27ae60;
  margin-right: 10px;
}
</style>