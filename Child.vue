<template>
<article>
    <p>{{message}}</p>
</article>
</template>

<script>
export default {
    props: {
        message: String
    },

    methods: {

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
    }
    p {
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-weight: bold;
    }
</style>