<!-- Photo.vue -->
<template>
    <div>
      <h2>{{ photo.title }}</h2>
      <img :src="photo.url" :alt="photo.title">
    </div>
  </template>
  
  <script>
  export default {
    props: ['photo']
  }
  </script>
  