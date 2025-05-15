<template>
    <div>
        <h2>Child Component B</h2>
        <ChildC></ChildC>
    </div>
</template>

<script>
import ChildC from './ChildC.vue';

    export default {
        name: 'ChildB',
        components: {
            ChildC,
        }
    }
</script>

<style scoped>

</style>