<template>
    <div>
        <h2>Options - {{o_firstName}}</h2>
        <h2>Composition - {{c_firstName}}</h2>
        <h2>Composition - {{greet}}</h2>
        <h2>Composition - {{c_firstName}} {{c_lastName}} {{c_heroName}}</h2>
        <h2>Composition - {{greethero}}</h2>
        <h2>Composition - {{state.firstName}} {{state.lastName}} {{state.heroName}}</h2>
        <h2>Composition - {{reactiveGreetHero}}</h2>

    </div>
</template>

<script>
import { ref, reactive } from 'vue';

    export default {
        name : 'DataComponent',
        setup () {
            const c_firstName =  ref('Clerk')
            const c_lastName =  ref('kent')
            const c_heroName =  ref('SuperMan')
            const greet = `Hello ${c_firstName.value}`
            const greethero = `Hello ${c_firstName.value}  ${c_lastName.value}  ${c_heroName.value}`
            
            const state = reactive({
                firstName : 'Princess',
                lastName : 'Diana',
                heroName : 'WonderWoman'
            })

            const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} ${state.heroName}`

            return {
                c_firstName, greet, c_lastName, c_heroName, greethero,
                state, reactiveGreetHero
            }
        },
        data () {
            return {
                o_firstName : 'Bruce',
                o_lastName : 'Wayne',
                o_herotName : 'Batman',
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>