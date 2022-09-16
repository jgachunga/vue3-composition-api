<template>
    <div>
        {{name}}
    </div>
</template>

<script>
import { ref } from 'vue'

    export default {
        name: 'DemoOne',
        setup() {
            let name = ref('John')

            setTimeout(() => {
                name.value = 'CodeVolution'
            }, 2000)
            return {
                name
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>