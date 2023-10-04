<template>
  <div class="px-4 md:px-40">
  <div id="app">
      <AddPostForm @add-post="addPostToArray" />
      <ul>
        <li v-for="post in posts" :key="post.id" class="w-full flex flex-col md:flex-row mt-10 bg-slate-100 rounded-xl overflow-hidden">
          <img src="https://source.unsplash.com/300x200/?technology" alt="" class="basis-1/4">
          <div class="ml-10 py-3">
            <h2 class="text-4xl font-semibold">{{ post.title }}</h2>
            <p class="mt-1">{{ post.content }}</p>
          </div>
        </li>
      </ul>
  </div>
  </div>
</template>

<script>
import AddPostForm from "./components/AddPost.vue";

export default {
 components: { 
    AddPostForm,
 },
 data() {
    return {
      posts: [],
    };
 },
 methods: {
    addPostToArray(post) {
      this.posts.push(post);
    },
 },
};
</script>