<!-- Album.vue -->
<template>
    <div>
      <h2>{{ album.title }}</h2>
      <p><strong>Usuário:</strong> {{ album.userId }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['album']
  }
  </script>
  