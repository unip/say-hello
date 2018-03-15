<template>
  <div id="app">
    <div v-bind:key v-for="message in messages">
      <h4>{{ message.title }}</h4>
      <p>{{ message.text }}</p>
      <p>{{ message.timestamp }}</p>
    </div>
  </div>
</template>

<script>
import Firebase from 'firebase'

let config = {
  apiKey: 'AIzaSyC8XVdZn1tVIhmRfqorm_dDN3rCIuSiZZs',
  authDomain: 'sayhello-6aa0b.firebaseapp.com',
  databaseURL: 'https://sayhello-6aa0b.firebaseio.com',
  projectId: 'sayhello-6aa0b',
  storageBucket: 'sayhello-6aa0b.appspot.com',
  messagingSenderId: '219017703278'
}

let app = Firebase.initializeApp(config)
let db = app.database()
let messagesRef = db.ref('messages')

export default {
  name: 'app',
  firebase: {
    messages: messagesRef
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
</style>
