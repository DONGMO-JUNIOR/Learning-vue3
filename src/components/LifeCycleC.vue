<template>
    <div>
Composition API Lifecycle Hooks
    </div>
</template>

<script>
import {
    onBeforeMount,
    onMounted,
    onBeforeUpdate,
    onUpdated,
    onBeforeUnmount,
    onUnmounted,
} from 'vue'

    export default {
        name: LifeCycleC,
        setup(){
            onBeforeMount(()=>{
            console.log('LifeCycleC onBeforeMount()')

        }),
        onMounted(()=>{
            console.log('LifeCycleC onMounted()')

        }),
        onBeforeUpdate(()=>{
            console.log('LifeCycleC onBeforeUpdate()')

        }),
        onUpdated(()=>{
            console.log('LifeCycleC onUpdated()')

        }),
        onBeforeUnmount(()=>{
            console.log('LifeCycleC onBeforeUnmounted()')

        }),
        onUnmounted(()=>{
            console.log('LifeCycleC unmounted()')

        })
        }
    }
</script>

<style scoped>

</style>