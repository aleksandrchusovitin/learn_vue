<template>
  <div class="root">
    <h1 style="margin-bottom: 15px;">Страница с постами</h1>
    <my-button style="margin-bottom: 15px;" @click="showDialog">Создать пост</my-button>
    <my-dialog v-model:show="isDialogVisible"><post-form @create="createPost" /></my-dialog>
    <post-list @remove="removePost" :posts="posts" />
  </div>
</template>

<script>
import PostForm from '@/components/PostForm.vue';
import PostList from '@/components/PostList.vue';

export default {
  components: {
    PostForm,
    PostList,
  },

  data() {
    return {
      posts: [
        { id: 1, title: 'Название поста', description: 'Описание поста' },
        { id: 2, title: 'Название поста 2', description: 'Описание поста 2' },
        { id: 3, title: 'Название поста 3', description: 'Описание поста 3' },
      ],
      isDialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.isDialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialog() {
      this.isDialogVisible = true;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.root {
  padding: 20px;
}
</style>
