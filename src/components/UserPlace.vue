<!-- UserPlace.vue -->
/* eslint-disable */
<template>
    <div>
      <h2>{{ user.name }}</h2>
      <p><strong>Email:</strong> {{ user.email }}</p>
      <p><strong>Telefone:</strong> {{ user.phone }}</p>
      <p><strong>Website:</strong> {{ user.website }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['user']
  }
  </script>
  