<template>
    <div>
        <input type="text" name="" placeholder="Reactive fname" id="" v-model="fName" />
        <input type="text" name="" placeholder="Reactive lname" id="" v-model="lName" />

        <h1>Options Full Name is  {{fullName}}</h1>

        <input type="text" name="" placeholder="heroName" id="" v-model="refFirstName" />
        <input type="text" name="" placeholder="firstName" id="" v-model="refLastName" />
        
        <h1>Composition Full Name is  {{refFullName}}</h1>

        
        <input type="text" name="" placeholder="heroName" id="" v-model="reactiveFirstName" />
        <input type="text" name="" placeholder="firstName" id="" v-model="reactiveLastName" />
        
        <h1>Reactive Full Name is  {{reactiveFullName}}</h1>

        <h1>watcher</h1>
        <input type="text" name="" placeholder="firstName" id="" v-model="firstName" />

    </div>
</template>

<script>
import { computed, reactive, ref, toRefs, watch } from 'vue';

    export default {
        name: 'VmodelComposition',
        setup () {
            const refFirstName = ref('')
            const refLastName = ref('')
            const firstName = ref('')
            
            const refFullName = computed(function() {
                return `${refFirstName.value} ${refLastName.value}`
            })

            const state = reactive({
                reactiveFirstName: '',
                reactiveLastName: '',
                fName: '',
                lName : ''
            })


            const reactiveFullName = computed(function() {
                return `${state.reactiveFirstName} ${state.reactiveLastName}`
            })

            // watch(() => {return {...state}}, function(newValue, oldValue) {
            //     console.log('old fname', oldValue.fName);
            //     console.log('new fname', newValue.fName);
            // },)

            watch(() => state.fName, function(newValue, oldValue) {
                console.log('old fname', oldValue);
                console.log('new fname', newValue);
            },)

            return {
                refFirstName,
                refLastName,
                refFullName,
                ...toRefs(state),
                reactiveFullName,
                firstName
            }
        },
        data () {
            return {
                
                name: ''
            }
        },
        computed: {
            fullName() {
                return `${this.fName} ${this.lName}`
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>