<script setup>
    let a = defineModel("str")
    defineProps({
        setTask: {
            type: Function,
            required: true
        }
    })
</script>


<template>
    <input placeholder="Name" v-model="a">
    <button @click="setTask(a)">Создать</button>
</template>

<style scoped>

</style>