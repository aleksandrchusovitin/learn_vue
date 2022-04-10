<template>
  <div class="post">
    <div>
      <h4>{{ post.title }}</h4>
      <p>{{ post.description }}</p>
    </div>
    <div>
      <my-button @click="$emit('remove', post)">Удалить</my-button>
      <my-button class="edit">Редактировать</my-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px;
  margin-bottom: 15px;
  border: 2px solid teal;
}

.edit {
  margin-left: 5px;
}
</style>
