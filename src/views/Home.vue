<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPost" :posts="posts" />
    <button @click="showPost = !showPost">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue"
import { ref } from 'vue'

export default {
  name: 'Home',

  components: {
    PostList
  },

  setup() {
    const posts = ref([
      {title: 'Welcome to the blog', body: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Alias expedita est repellat optio quidem velit ipsam totam possimus unde, ducimus libero, magni fugit veritatis, laboriosam eligendi ipsum odit esse? Laborum autem repudiandae nesciunt aperiam sapiente voluptas officia iusto, aspernatur, modi voluptatibus dolore inventore assumenda itaque unde necessitatibus temporibus. Quae harum eveniet sapiente, vitae aperiam magnam laudantium quas in magni aliquid enim dignissimos, maiores dolorum dolorem nihil sit cupiditate nulla provident consectetur quia? Provident id temporibus placeat ullam? Ducimus, dignissimos? Magnam quidem voluptate rem, quae dignissimos fugiat architecto dolorum beatae sapiente, cumque delectus tempora consequatur in ab voluptatem, eius accusantium? Quo!', id: 1},
      {title: 'Top 5 CSS tips', body: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Alias expedita est repellat optio quidem velit ipsam totam possimus unde, ducimus libero, magni fugit veritatis, laboriosam eligendi ipsum odit esse? Laborum autem repudiandae nesciunt aperiam sapiente voluptas officia iusto, aspernatur, modi voluptatibus dolore inventore assumenda itaque unde necessitatibus temporibus. Quae harum eveniet sapiente, vitae aperiam magnam laudantium quas in magni aliquid enim dignissimos, maiores dolorum dolorem nihil sit cupiditate nulla provident consectetur quia? Provident id temporibus placeat ullam? Ducimus, dignissimos? Magnam quidem voluptate rem, quae dignissimos fugiat architecto dolorum beatae sapiente, cumque delectus tempora consequatur in ab voluptatem, eius accusantium? Quo!', id: 2}
    ])

    const showPost = ref(true)
   
    return {posts, showPost}
  }
}
</script>
