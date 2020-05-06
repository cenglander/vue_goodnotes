<template>
<article>
    <p>{{message}}</p>
    <!-- <p>{{input}}</p> -->
    <button v-on:click="removeTodo">Delete this Todo</button>
</article>
</template>

<script>
export default {
    props: {
        message: String,
        input: String,
    },

    methods: {
        removeTodo() {
            this.$emit('remove', this.message)
        }
    }
}
</script>

<style>
    article {
        background: #FC9F5B;
        width: 15vw;
        height: 15vh;
        padding: 1em;
        margin: 1em;
        border-radius: 3px;
    }
    p {
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-weight: bold;
    }
</style>