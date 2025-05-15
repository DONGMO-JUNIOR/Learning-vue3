<template>
    <div>
        <button @mouseover="incrementCount">Hovered {{ count }} times</button>
    </div>
</template>

<script>
import useCounter from '@/composables/useCounter';
// import CounterMixin from './mixins/counter';
    export default {
        name: 'HoverCounter',

        setup(){
          const {count, incrementCount} = useCounter()

          return {
            count,incrementCount
          }
        }
        // mixins: [CounterMixin],
    }
</script>

<style scoped>

</style>