<template>
    <div>
        <div>Option API LifeCycle Hooks</div>
    </div>
</template>

<script>

    export default {
        name: 'LifeCycleO',

        beforeCreate(){
            console.log('LifeCycleO beforeCreate()')
        },
        created(){
            console.log('LifeCycleO Create()')
           
        },
        beforeMount(){
            console.log('LifeCycleO beforeMount()')

        },
        mounted(){
            console.log('LifeCycleO mounted()')

        },
        beforeUpdate(){
            console.log('LifeCycleO beforeUpdate()')

        },
        updated(){
            console.log('LifeCycleO updated()')

        },
        beforeUnmount(){
            console.log('LifeCycleO beforeUnmounted()')

        },
        unmounted(){
            console.log('LifeCycleO unmounted()')

        }
    }
</script>

<style scoped>

</style>