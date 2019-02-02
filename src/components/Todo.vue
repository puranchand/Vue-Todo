<template>
  <div class="hello">
    <h1>Todo List Created in Vue.js</h1>
    <div>
      <input v-model="message" placeholder="Edit Me"/>
      <button type='button' v-on:click="addText()">Add Click</button>
     <ul>
       <li v-for="(todo,index) in todos" >
        {{index +1}} {{todo}} 
         <button type='button'  v-on:click="deleteText(todo)">x</button>
       </li>
     </ul>
    </div>
  
  </div>
</template>

<script>

export default {
  
  name: 'Todo',

  data() {
    return {
      todos:[],
      message:'',
    }
  },

  methods: {
    addText() {
      this.todos.push(this.message);
      this.message = ''
    },

    deleteText(todo) {
      const Index = this.todos.indexOf(todo);
      this.todos.splice(Index, 1);
    },
    
  },

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
  
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
