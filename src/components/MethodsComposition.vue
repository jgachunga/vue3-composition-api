<template>
    <div>
        <h2>{{name}}</h2>
        <button @click="setName">Change Name</button>

        <h2>{{count}}</h2>
        <button @click="incrementCount">Increment Count</button>

        <h2>{{first}} {{last}}</h2>
        <button @click="changeHero">change Hero</button>


    </div>
</template>

<script>
import { reactive, ref, toRefs } from 'vue'

    export default {
        name : 'MethodsComposition',
        setup () {
            const count = ref(0)
            const state = reactive({
                first: 'Bruce',
                last : 'Wayne'
            })

            function incrementCount() {
                count.value +=1
            }

            function changeHero() {
                state.first = 'Clark'
                state.last = 'kent'
            }

            return {
                count,
                incrementCount,
                ...toRefs(state),
                changeHero
            }
        },
        data () {
            return {
                name : 'John'
            }
        },
        methods: {
            setName() {
                this.name = "CodeVolution"
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>