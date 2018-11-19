<template>
  <div>
    <p>{{ wildcard }}</p>

    <Post :post="post" />
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
      wildcard: this.$route.params.id
    }
  },
  async asyncData ({ params, app }) {
    let data = await app.$axios.$get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)

    return { post: data }
  }
}
</script>
