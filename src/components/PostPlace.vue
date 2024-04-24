<!-- Post.vue -->
<template>
    <div>
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['post']
  }
  </script>
  