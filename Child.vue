<template>
<article>
    <!-- <p>{{input}}</p> -->
    <p>{{post}}</p>
    <button v-on:click="editTodo">Edit this Todo</button>
    <button v-on:click="removeTodo">Delete this Todo</button>
</article>
</template>

<script>
export default {
    props: {
        // post: Object,
        post: String,
        // input: String,
    },

    methods: {
        editTodo() {
            this.$emit('edit', this.post)
        },
        removeTodo() {
            this.$emit('remove', this.post)
        }
    }
}
</script>


<style>
    article {
        background: #FC9F5B;
        width: 15vw;
        height: 15vh;
        padding: 1rem;
        margin: 1rem;
        border-radius: 3px;

    }
    p {
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-weight: bold;
        margin: 0.3rem;
    }
    /*  */
    textarea {
        white-space: pre-line;
    }

</style>