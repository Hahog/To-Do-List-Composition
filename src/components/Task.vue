<script setup>
    import { ref } from 'vue'
    let str = ref("");
    let bol = ref(false);
   let obj = defineProps({
       "str": String,
       "idTask": Number,
       "delTask": Function,
       "renameTask": Function
   })
   
   //str = str.str
   
</script>

<template>
    <section className="task">
        <h1 v-if="!bol">{{ obj.str }}</h1>
        <input placeholder="Name" v-if="bol" v-model="str">
        <section className="but">
            <button @click="obj.delTask(obj.idTask)">Delete</button>
            <button v-if="!bol" @click="bol = !bol">Rename</button>
            <button v-if="bol" @click=" bol = !bol, obj.renameTask(obj.idTask, str)">Edit</button>
        </section>
    </section>
</template>

<style scoped>
    .task {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        gap:40px;
        padding: 15px;
        background-color: bisque;
        border: 1px solid black;
        border-radius: 10px;
        width: 100vw;
        margin: 5px;
        font-size: 20px;
    }

    button {
        width: 100px;
        height: 30px;
        border: none;
        background-color: aqua;
        color:black;
        border-radius: 10px;
        padding: 7px;
        font-size: 15px;
        font-weight: bold;
        font-style: italic;
        text-align: center;
    }

    .but {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 150px;
        
    }
</style>