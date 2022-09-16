<template>
    <div>
        {{state.firstName}} {{state.lastName}}
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'

    export default {
        name: 'DemoOne',
        setup() {
           const state = reactive({
            firstName : 'Bruce',
            lastName : 'Wayne'
           })
           return toRefs(state)
        }
    }
</script>

<style lang="scss" scoped>

</style>