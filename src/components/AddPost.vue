<template>
 <div>
    <h1 class="text-center text-4xl font-semibold mt-10">Add Post</h1>
    <form @submit.prevent="addPost">
      <div>
        <label for="title" class="font-semibold">Title:</label>
        <input type="text" id="title" v-model="title" required class="ring-2 mb-3 w-full py-2 rounded-md px-2"/>
      </div> 
      <div>
        <label for="content" class="font-semibold">Content:</label>
        <textarea id="content" v-model="content" required class="ring-2 w-full rounded-md px-2 py-1" rows="4"></textarea>

      </div>
      <div class="w-full flex justify-center mt-3">

        <button type="submit" class="px-4 py-3 bg-sky-900 text-white rounded-2xl font-bold w-full md:w-fit ">Add Post</button>
      </div>
    </form>
 </div>
</template>

<script>
export default {
 data() {
    return {
      title: "",
      content: "",
    };
 },
 methods: {
    addPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        content: this.content,
      };
      this.$emit("add-post", newPost);
      this.title = "";
      this.content = "";
    },
 },
};
</script>