
<template>
  <div id="app">
    <h1> To-do list </h1>
    <input type="text" v-on:keyup.enter="addTodo()" v-model="text">
    <ul>
      <li v-for="(item, index) in list" v-bind:key="item" >
        <TodoItem :item="item" @remove="removeTodo(index)" />
      </li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/todo-item.vue'

export default {
  components: {
    TodoItem
  },
  data(){
    return {
      text: '',
      list: [{text: 'Adicionarr mais itens á lista'}]
    }
  },
  methods:{
    addTodo(){
      this.list.push({text: this.text})
      this.text = ''
      
    },
    removeTodo(index){
      this.list.splice(index, 1)
    }
  }
}
</script>

