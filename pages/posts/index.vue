<template>
  <div>
    <Post v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>

<script>
import Post from '@/components/Post'

export default {
  components: {
    Post
  },
  data () {
    return {
      posts: []
    }
  },
  methods: {
    async fetchPosts () {
      let posts = await this.$axios.$get('https://jsonplaceholder.typicode.com/posts')

      return this.posts = posts
    }
  },
  mounted () {
    this.fetchPosts()
  }
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  max-width: 940px;
  width: 100%;
  align-items: center;
  margin: 60px auto;
}
</style>
