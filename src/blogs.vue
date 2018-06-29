<template>
<div class="blogs">
  <h2>{{ blogTitle }}</h2>
  <input type="text" v-model="searchTerm" />
  <button @click="changeTitle">Change title</button>
  <div v-for="post in filteredPosts" :key="post.id">
  <h3>{{ post.title }}</h3>
  <p>{{ post.body | snippet}}</p>
  </div>

</div>
</template>


<script>
import axios from 'axios'
export default {
  name: 'Blogs',
  data() {
    return {
      blogTitle: 'blogs',
      posts: [],
      searchTerm: ''
    }
  },
  methods: {
    changeTitle () {
         this.blogTitle = "Brents amazing blog stuff"
    }
  },
  computed: {
      filteredPosts () {
        return this.posts.filter(post => {
          return post.title.match(this.searchTerm)
        })
      }
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/posts/').then(Response =>  {
          console.log(Response)
          this.posts = Response.data
    }).catch(err => {
      console.log(err)
    })
  }

}
</script>
