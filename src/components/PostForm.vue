<template>
  <form @submit.prevent class="form">
    <h3 class="form-title">Создание поста</h3>
    <label for="title">
      <my-input
        v-model="post.title"
        class="input"
        id="title"
        name="title"
        type="text"
        placeholder="Название"
      />
    </label>

    <my-input
      v-model="post.description"
      class="input"
      id="description"
      name="description"
      type="text"
      placeholder="Описание"
      :label="Описание"
    />

    <my-button class="createButton" @click="createPost">Создать</my-button>
  </form>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  data() {
    return {
      post: {
        title: '',
        description: '',
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = uuidv4();
      this.$emit('create', this.post);
      this.post = {
        title: '',
        description: '',
      };
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}

.form-title {
  margin-bottom: 10px;
}

.createButton {
  margin-bottom: 15px;
  align-self: flex-end;
}
</style>
