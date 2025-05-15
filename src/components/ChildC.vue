<template>
    <div>
        <h2>Child Component C</h2>
        <h3>Child Component C username - {{ userName }}</h3>

        <h3>Child Composition C compostion username - {{ ChildUsername }}</h3>
  
        <h3>Child component C Count-- {{ chilCount }}</h3>
        <h3>Child component C Hero-- {{ firstName}}..{{ lastName }}</h3>

         
  <!-- <button @click="incremention">Incrémenter depuis l’enfant</button> -->
  <button @click="incrementCount">Increment count from child </button>

        
    </div>
</template>

<script> 
import { inject,toRefs } from 'vue';
    export default {
        name: 'ChildC',
        setup(){
            // const count = ref(0)
            // const incremention = inject('increment')
            const ChildUsername = inject('yo', 'Default username')


            const chilCount = inject('c_count', 0)
            const chilHero = inject ('c_hero',{})
            const incrementCount = inject('incrementCount')
            return {
                ChildUsername, 
                chilCount,
                ...toRefs(chilHero),
                incrementCount

                // count,
                // incremention 
            }
               },

        inject: ['userName'],
       
    }
</script>

<style scoped>

</style>b