<!-- App.vue -->
<template>
  <div>
    <h1>Usuários</h1>
    <div v-for="user in users" :key="user.id">
      <h2>{{ user.name }}</h2>
      <p><strong>Email:</strong> {{ user.email }}</p>
      <p><strong>Telefone:</strong> {{ user.phone }}</p>
      <p><strong>Website:</strong> {{ user.website }}</p>
      <h3>Postagens</h3>
      <Post v-for="post in user.posts" :key="post.id" :post="post" />
      <h3>Álbuns</h3>
      <Album v-for="album in user.albums" :key="album.id" :album="album" />
      <h3>Fotos</h3>
      <Photo v-for="photo in user.photos" :key="photo.id" :photo="photo" />
      <h3>Comentários</h3>
      <Comment v-for="comment in user.comments" :key="comment.id" :comment="comment" />
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Post from './components/PostPlace.vue';
import Album from './components/AlbumPlace.vue';
import Photo from './components/PhotoPlace.vue';
import Comment from './components/CommentPlace.vue';

export default {
  name: 'App',
  components: {
    Post,
    Album,
    Photo,
    Comment
  },
  data() {
    return {
      users: []
    };
  },
  async created() {
    await this.fetchUsers();
  },
  methods: {
    async fetchUsers() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/users?_embed=posts&_embed=albums&_embed=photos&_embed=comments');
        this.users = response.data;
      } catch (error) {
        console.error('Erro ao buscar usuários:', error);
      }
    }
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
