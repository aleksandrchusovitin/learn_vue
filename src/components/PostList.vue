<template>
  <div>
    <h3 class="title">Список постов:</h3>
    <post-item v-for="post in posts" :post="post" :key="post.id" />
  </div>
</template>

<script>
import PostItem from '@/components/PostItem.vue';

export default {
  components: {
    PostItem,
  },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.title {
  margin-bottom: 15px;
}
</style>
