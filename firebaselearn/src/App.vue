<template>
<div>
  <AddPost/>
  <PostsPage/>
  <ArticlePage/>
</div>
</template>

<script>
import AddPost from './components/AddPost.vue'
import PostsPage from './components/PostsPage.vue'
import ArticlePage from './components/ArticlePage.vue'

export default {
  name: 'App',
  components: {
    AddPost,
    PostsPage,
    ArticlePage,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
