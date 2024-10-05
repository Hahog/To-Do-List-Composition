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
    <section className="inp">
        <input placeholder="Name" v-model="a">
        <button @click="setTask(a)">Создать</button>
    </section>
</template>

<style scoped>
 p {
    color:white;
    margin: 0;
 }

 .inp {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;
    gap:10px;
    
 }
</style>