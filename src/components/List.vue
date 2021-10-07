<template>
     <div>
         <div>
              <input type="text" v-model="newTodo">
              <button 
              @click="addTodo()"

              >Add</button>
         </div>
         <div class="List">
             <Todo 
             v-for="(todo,index) in todos" 
             :key="index"
             :todo="todo"
             :deleteTodo = "deleteTodo" 
             :index="index"
             />
         </div>
    </div>
    
</template>

<script>
import Todo from './Todo.vue'

export default {
    data(){
        return {
            newTodo: '',
            todos: [
               
            ]
        }
    },
    methods:{
        addTodo(){
            this.todos.push({
                content:this.newTodo, 
                done:false
            });
            this.newTodo = '';
        },
        deleteTodo(index){
            this.todos.splice(index,1);
        }
    },
    components: {
        Todo    
    }
}
</script>

<style scoped>

</style>
