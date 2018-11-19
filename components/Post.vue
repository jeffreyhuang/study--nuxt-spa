<template>
  <div class="post">
    <h1>{{ post.title }}</h1>

    <p>{{ post.body }}</p>
  </div>
</template>

<script>
export default {
  props: {
    post: Object
  }
}
</script>
