<template>
    <div>
        Hello {{ fullName }}

        <button @click="sendEvent"> Call Heroes</button>
    <!-- Hello {{ firstName }} {{  lastName }}   -->
    <!-- <h3></h3> -->
    </div>
</template>

<script>
import { computed } from 'vue';
    export default {
        name: 'PersonGreeting',
        setup(props, context){
            console.log(context);
            
            const fullName = computed( () => {
                return `${props.firstName} ${props.lastName}`
            })
            function sendEvent(){
                context.emit('callHeroes', fullName.value)
            }


            return {
                fullName,
                sendEvent
                    }
        },
         props: ['firstName','lastName'],
         emits: ['callheroes'],
        // computed: {
        //     fullName(){
        //         return `${this.firstName} ${this.lastName}`
        //     }
        // }
    }
</script>

<style scoped>

</style>