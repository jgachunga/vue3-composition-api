<template>
    <h2>Hello {{name}}</h2>
</template>

<script>
    export default {
        name: 'GreetComponent',
        props: ["name"]
    }
</script>

<style scoped>

</style>