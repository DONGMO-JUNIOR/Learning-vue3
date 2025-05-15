<template>
    <div>
        <input type="text" placeholder="First Name" v-model="firstName" />
        <input type="text" placeholder="Last Name" v-model="lastName" />

        <PersonGreeting :firstName="firstName" :lastName="lastName" @callHeroes="callHeroes"></PersonGreeting>

    </div>
</template>

<script>  
import {ref} from 'vue'
import PersonGreeting from './PersonGreeting.vue'
    export default {
        name: 'PersonApp',
        components: {
            PersonGreeting,
        },
        setup(){
            const firstName = ref('')
            const lastName = ref('')
            function callHeroes(hero) {
                alert(`calling ${hero}`)
            }

            return {
                firstName,
                lastName,
                callHeroes
            }
        }
    }
</script>

<style scoped>

</style>