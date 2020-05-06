<template>
<main>
    <h1>Goodnotes - Vue</h1>
    <input type="text" v-model="input" v-on:click="input=''">
    <button v-on:click="addTodo">Add Todo</button>

    <Child
     
    />

    <Child
        v-for="child in todoList"
        v-bind:key="child"
        v-bind:message="child"
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
        input: "Type your TODO here..",
        todoList: ["Broccoli", "Tomatos", "Cabbage"]

    }),

    methods: {
        addTodo(input, todoList) {
            todoList.push(input)
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

</style>