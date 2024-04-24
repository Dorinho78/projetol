<!-- Comment.vue -->
<template>
    <div>
      <h4>{{ comment.name }}</h4>
      <p>{{ comment.body }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['comment']
  }
  </script>
  