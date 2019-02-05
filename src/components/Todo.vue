<template>
    <div class="container mx-auto hello">
    <h1>Todo List Created in Vue.js</h1>
    <div class="mx-auto">
      <!-- <input  placeholder="Edit Me"/>
      <button class="btn btn-primary" type='button' >Add Click</button> -->
      <div class="input-group mb-3 addInput">
        <input type="text" class="form-control" v-model="message" placeholder="Add text" aria-label="Recipient's username" aria-describedby="basic-addon2">
        <div class="input-group-append">
          <span class="input-group-text" id="basic-addon2" v-on:click="addText()">@Add</span>
        </div>
      </div>
      <div class="card align-center" style="width: 18rem;">
        <ul class="list-group list-group-flush">
          <li  class="list-group-item" v-for="(todo,index) in todos" :key="index" >
              <div class="btn-group" role="group" aria-label="Basic example">
                <button type="button" class="btn btn-secondary" > {{index+1}} </button>
                <button type="button" class="btn btn-secondary centerBtn"> {{todo}} </button>
                <button class="btn btn-secondary" type='button'  v-on:click="deleteText(todo)">x</button>
              </div>
          
            
          </li>
        </ul>
      </div>
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

.centerBtn{
  min-width: 150px;
}



.addInput {
    width: 400px;
}
</style>
