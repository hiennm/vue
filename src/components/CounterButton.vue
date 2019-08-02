<template>
    <button @click="count++">Clicked {{count}} times.</button>
</template>

<script>
export default {
    name: 'CounterButton',
    props: {
        count: Number
    }
    
}
</script>

<style scoped>

</style>
