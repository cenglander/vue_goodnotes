<template>
<!-- <main v-bind:class="{layout-grid: grid}"> -->
<main>
    <h1>GOODNOTES - Vue</h1>

    <!-- textarea istället för input-->
    <!-- textarea rows="5"-->
    <input
        type="text" 
        v-model="input" 
        placeholder="Type your TODO here">
    <button 
        v-on:click="addTodo(input, todoList)">Add Todo</button>

    <!-- <Child        
    /> -->

    <Child
        v-for="child in todoList"
        v-bind:key="child"
        v-bind:post="child"
        v-on:edit="editPost"
        v-on:remove="removePost"

    />
    
</main>
</template>

<script>
import Child from './Child'
export default {
    name: 'App',
    components: {
        Child: Child
    },

    data: () => ({
        //input: "",
        // todoList: ["Broccoli", "Tomatos", "Cabbage"],
        todoList: [],
        grid: false, //test - toggla klassen layout-grid

    }),

    methods: {
        addTodo(input, todoList) {
            // todoList.push(input)
            todoList.unshift(input)
        },
        editPost(payload) {            
            console.log(payload)
        },
        removePost(payload) {
            this.todoList = this.todoList.filter(post => post != payload)
            console.log(this.todoList)
        }
    }

}
</script>


<style>
    body {
        margin: 0;
        padding: 0;
        background: #ECE4B7;
        display: flex;
        justify-content: center;
    }
    /* test för grid-layout */
    .layout-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }
    button {
        border-radius: 5px;
        background: #FBD1A2;
        padding: 0.3rem;
        margin: 1rem;
    }

</style>

<!--
sandy brown (orange/brown) FC9F5B
light orange FBD1A2
lemon meringue ECE4B7
middle blue green 7DCFB6
emerald 33CA7F

-->

