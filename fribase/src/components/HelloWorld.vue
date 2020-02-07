<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
    <input type="text" v-model="name" >
     <input type="text" v-model="lastname" >
     <button @click="insertToContact(name,lastname)">Add</button>
    </div>
    <hr>
    <ul  :key="key" v-for="(contact, key) in contacts">
    <li v-if="updateKey === key">
    <input type="text" v-model="updateName">
    <input type="text" v-model="updateLastname">
    <button @click="updateToContact(updateName,updateLastname)">save</button>
    </li>
    <li v-else>
  {{contact.name}} : {{contact.lastname}}
  <button @click="setUpdateToContact(key,contact)">update</button>
  <button @click="deleteToContact(key)">delete</button>
  </li>
  </ul>
  </div>
  
</template>

<script>

import * as firebase form 'firebase'

var config ={
    apiKey: "AIzaSyASPgbLiHdw4slL4gr3LKU_X0GWns1t3bM",
    authDomain: "nuyvue.firebaseapp.com",
    databaseURL: "https://nuyvue.firebaseio.com",
    projectId: "nuyvue",
    storageBucket: "nuyvue.appspot.com",
    messagingSenderId: "437262995395",
    appId: "1:437262995395:web:60a8ded047625d6a327776",
    measurementId: "G-RXGRBSFZFS"
}
firebase.initializeApp(firebaseConfig);
firebase.analytics();
var contactRef = database.ref('/contacts')
var database = firebase.database()
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
