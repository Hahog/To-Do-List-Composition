<script setup>
  import {ref} from 'vue'
  import Inp from './components/Inp.vue'
  import Task from './components/Task.vue'
  let a = ref("0");
  let ar = ref([]);
  function setTask(str) {
    ar.value.splice(0,0,str)
    a.value = "";
  }
</script>

<template>
  <section className="inp">
    <Inp v-model:str="a" :setTask="setTask"></Inp>
  </section>
  <section className="task">
    <Task  v-for="i in ar" :key="i" :str="i"></Task>
  </section>
</template>

<style scoped>
  .task {
    display: flex;
    justify-content: center;
  }
  .inp {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;
    gap:10px;
    padding: 40px;
  }
</style>
