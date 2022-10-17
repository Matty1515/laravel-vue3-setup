<script setup>
    import { reactive, onMounted } from 'vue';

    const state = reactive({
        remf: "remfer",
        isRemf: true,
    });

    onMounted(() => {
        fetch("/exampleconfig")
            .then(response => response.json())
            .then(data => (console.log(data)));
    });
</script>

<template>
    <main>
        <h1>Laravel 9 with vue 3</h1>
        <p>{{ state.remf }}</p>
        <p>Is a remf? {{ state.isRemf }}</p>
    </main>
</template>

<style>
    body {
        background-color: whitesmoke;
        text-align: center;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    main {
        max-width: 360px;
        background-color: white;
        padding: 40px;
        border-radius: 20px;
        margin: 20px auto;
    }
</style>