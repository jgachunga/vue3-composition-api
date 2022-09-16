<template>
    <div>
        <card-component >

        </card-component>
        <card-component >
            <template v-slot:header>
                <h2>Header</h2>
            </template>
        </card-component>
        <card-component >
            <template v-slot:body>
                <h2>This is the card body</h2>
            </template>
        </card-component>
    </div>
</template>

<script>
import CardComponent from './components/CardComponent.vue';
    export default {
    components: { CardComponent }
}
</script>

<style lang="scss" scoped>

</style>