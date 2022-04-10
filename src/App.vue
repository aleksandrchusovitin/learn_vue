<template>
  <div class="root">
    <post-form @create="createPost" />
    <post-list :posts="posts" />
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
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
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
