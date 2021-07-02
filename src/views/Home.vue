<template>
    <div class="bg-gray-50">
      <div class="max-w-screen-xl px-4 py-12 mx-auto sm:px-6 lg:py-16 lg:px-8 lg:flex lg:items-center lg:justify-center">
        
            <form v-on:submit.prevent="addNewTodo">
             <div class=" row flex mt-8 lg:flex-shrink-0 lg:mt-0 justify-center">
             <input v-model="newTodo" name="newTodo" type="text" placeholder="Enter Task" class=" bg-gray-200 justify-center appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-indigo-500" >
             <button  class=" inline-flex items-center justify-center px-5 py-3 text-base font-medium leading-4 text-indigo-600  ease-in-out bg-white border border-transparent rounded-md hover:text-indigo-500 focus:outline-none">Add</button>
            </div>
            </form>
         <ul>
             <li  v-for="todo in todos" v-bind:key="todo.id">
                <h3>{{todo.content}}</h3>
             </li>
         </ul>
      </div>

    </div>

</template>



<script setup>
import {ref} from "vue";
const newTodo= ref('');
const todos = ref([]);

//addNewTodo function
function addNewTodo() {
  todos.value.push({
    id: Date.now(),
    done: false,
    content: newTodo.value,
});
newTodo.value = "";
} 

</script>