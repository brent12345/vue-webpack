<template>
  <div id="app">
    <Navbar />
    <Blogs />
    <AllFriends :friends="friends" @delete="deleteFriend"/>
    <OnlineFriends :friends="friends" />
    <h1>{{ title }}</h1>
  </div>
</template>

<script>
  import Navbar from './Navbar'
  import AllFriends from './AllFriends'
  import OnlineFriends from './OnlineFriends'
  import Blogs from './Blogs'
  export default {
    name: 'app',
    components: {
      Navbar,
      OnlineFriends,
      AllFriends,
      Blogs

    },
    data() {
      return {
        title: 'My first vue app by brent',
        friends: [{
            name: 'brent',
            online: true
          },
          {
            name: 'Patrick',
            online: true
          },
          {
            name: 'James',
            online: false
          },
          {
            name: 'Mike',
            online: true
          },
          {
            name: 'Dr. B',
            online: false
          }
        ]
      }
    },
    methods: {
      deleteFriend (payload) {
        console.log(payload)
        this.friends = this.friends.filter(friend => {
          return friend.name !== payload.name
        })
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  h1,
  h2 {
    color: aqua;
    font-weight: bold;
  }
</style>
