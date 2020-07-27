<template>
  <div class="blog">
    <ul class="list-unstyled">
      <li class="media" v-for="post in posts" :key="post.id">
        <div class="media-body">
          <h5 class="mt-0 mb-1">{{ post.title }}</h5>
          {{ post.body }}
        </div>
      </li>
    </ul>

    
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'Blog',
  data() {
    return {
      posts: []
    }
  },

  methods: {
    getData(){
      var cmp = this;
      axios.get('https://jsonplaceholder.typicode.com/posts')
          .then(function (response) {
            cmp.posts = response.data;
          })
          .catch(function (error) {
            console.log(error);
          })
          .then(function () {
            // always executed
          });
    }
  },

  beforeMount() {
    this.getData()
  }
}
</script>