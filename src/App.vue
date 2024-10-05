<script setup>
  import {ref} from 'vue'
  import Inp from './components/Inp.vue'
  import Task from './components/Task.vue'
  let a = ref("");
  let ar = ref([]);
  let error = ref("");
  function setTask(str) {
    if(str) {
      error.value = ""
      ar.value.splice(0,0,str)
      a.value = "";
    } else {
      error.value = "Название не может быть пустым"
    }
  }
  function delTask (id) {
    ar.value.splice(id,1)
  }

  function renameTask(id, str) {
    ar.value.splice(id, 1, str)
  }
</script>

<template>
  <section className="inpu">
      <Inp v-model:str="a" :setTask="setTask"></Inp>
    <article className="error" v-if="error">
      <p v-if="error">{{ error }}</p>
    </article>
  </section>
  <section className="task">
    <Task  v-for="(i, id) in ar" :key="id" :delTask="delTask" :renameTask="renameTask" :idTask="id" :str="i"></Task>
  </section>
</template>

<style scoped>
  .task {
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  .inpu {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap:10px;
    padding: 40px;
  }

  p {
    margin: 0;
    padding: 0;
  }

  .error {
    background-color: red;
    align-items: center;
    padding: 5px;
    border-radius: 5px;
    font-size: 20px;
    font-weight: 600;
  }
</style>
