<template>
   <div>
       <!-- <input type="checkbox" name="" id="" v-model="todo.done"> -->
       <span 
       class="checkbox" 
       :class="{checked:todo.done}"
       @click="todo.done = !todo.done"
       ></span>
       <span :class="{done: todo.done}">
           {{todo.content}}
           <a href="#" @click.prevent="deleteTodo(index)">Xóa</a>
           </span>
   </div>
</template>

<script>


export default {
    props:['todo','deleteTodo','index']
}
</script>

<style scoped>
    span.done{
        text-decoration: line-through;
    }
    .checkbox {
        display: inline-block;
        width: 20px;
        height: 20px;
       border: 1px solid black;
    }

    .checkbox.checked{
        background-color: red;
    }
</style>
