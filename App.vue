<template>
<main>
    <Child
        v-for="child in list"
        v-bind:key="child"
        v-bind:message="child"

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
        list: ["Broccoli", "Carrot", "Tomato", "Cabbage"]

    }),

    methods: {

    }

}
</script>

<style>
    body {
        margin: 0;
        padding: 0;
        background: #ECE4B7;
    }

</style>