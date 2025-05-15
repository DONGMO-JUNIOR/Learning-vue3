<template>
    <div>
        <!--options API-->
        <input type="text" placeholder=" Name" v-model="name" />

        <!--composition API-->
        <input type="text" placeholder = " First Name" v-model="firstName" />
        <input type="text" placeholder = " Last Name" v-model="lastName" />


        <input type="text" placeholder = " Reactie firstName" v-model="fName" />
        <input type="text" placeholder = " Reactie LastName" v-model="lName" />

        <input type="text" placeholder = " Reactie Hero Name" v-model="options.heroName" />


    </div>
</template>

<script>
import _ from 'lodash'
import {ref, watch, reactive, toRefs} from 'vue'
    export default {
        name: 'WatchApp', 

        setup(){

            const state = reactive({
                fName: '',
                lName: '',
                options: {heroName: '' }
            })

            // watch(() => {
            //     return {...state}
            // }, function(newValue, oldValue) {
            //      console.log('fName Old value', oldValue.fName)
            //      console.log('fName New value', newValue.fName)
            //      console.log('lName Old value', oldValue.lName)
            //      console.log('lName New value', newValue.lName)
            // }) 
            watch( () => _.cloneDeep(state.options),
                function(newValue, oldValue) {
                 console.log('fName Old value', oldValue)
                 console.log('fName New value', newValue)},
                {deep: true})

            const firstName = ref('')
            const lastName = ref('Wayne')

            watch([firstName, lastName ],(newValue, oldValue) => {
                console.log(' firtName Old value', oldValue[0])
                console.log(' firtName New value ', newValue[0])

                console.log(' lastName Old value', oldValue[1])
                console.log(' lastName New value ', newValue[1])
                       },
                       {
                       immediate: true})
            return {
                firstName,
                lastName,
                ...toRefs(state)
            }
        }, 

        data(){
            return{
                name: '',
            }
        },
        watch: {
            name(newValue, oldValue) {
                console.log('Old value', oldValue)
                console.log('New value ', newValue)
            }
        }

    }
</script>

<style scoped>

</style>