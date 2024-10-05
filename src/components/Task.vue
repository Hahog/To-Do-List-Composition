<script setup>
   let str = defineProps(["str"])
   str = str.str
    console.log(str)
  
</script>

<template>
    <section className="task">
        <h1>{{ str }}</h1>
        <section className="but">
            <button>Delete</button>
            <button>Rename</button>
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