<template>
  <p v-if="isLoading">Loading...</p>
  <hr>
  <div v-for="p in post" :key="p.id">
    <h2>{{ p.id }} - {{ p.title }}</h2>
    <p>{{ p.body }}</p>
  </div>
</template>

<script>
export default {
    name: 'PlaceHolderPosts',
    data() {
      return {
        post: [],
        isLoading: false
      }
    },
    methods: {
      getPosts() {
        this.isLoading = true;

        fetch('https://jsonplaceholder.typicode.com/posts/')
        .then(function (response) {
          return response.json()
        })
        .then(data =>{
          this.post = data
          this.isLoading = false
        })
      }
    },
    mounted() {
      this.getPosts()
    }
}

</script>
