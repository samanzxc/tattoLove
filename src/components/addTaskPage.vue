<script setup>
import { ref } from 'vue'
import { task } from './globarVar'
import { id } from './globarVar'

const taskItems = JSON.parse(localStorage.getItem('taskItem'))

if (taskItems) {
    task.value = taskItems
}

const taskText = ref(null)

let min = 0
let sec = 0
let secondSec = 0

function addTask() {
  if (taskText.value) {
    task.value.push({
      id: ++id.value,
      text: taskText.value,
      timer: [min, sec, secondSec],
      timerActive: false,
    })
    taskText.value = ''
  }
  localStorage.setItem('taskItem', JSON.stringify(task.value))
}
</script>

<template>
  <div class="addTask__container">
    <p>Добавить задачу</p>
    <form action="/" @submit.prevent="addTask">
      <input v-model="taskText" type="text" placeholder="Введите задачу..." />
      <button type="submit">Добавить</button>
    </form>
    <img src="/src/assets/img/addTask.png" alt="" />
  </div>
</template>

<style scoped>
.addTask__container {
  padding-top: 150px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 75px;
}
.addTask__container p {
  font-size: 35px;
  font-weight: bold;
  color: var(--btn-collor);
}
.addTask__container form {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 15px 10px;
  background-color: #5a3686;
  width: 500px;
  text-align: center;
  row-gap: 20px;
  border-radius: 10px;
  margin-bottom: 50px;
}
.addTask__container form input {
  width: 100%;
  padding: 15px;
  border-radius: 10px;
  background-color: #ffffff3d;
  border: none;
  font-size: 19px;
  color: #fff;
}
.addTask__container form input::placeholder {
  color: #ffffff65;
}
.addTask__container form input:focus {
  outline: none;
}
.addTask__container form button {
  border-radius: 10px;
  background: rgb(196, 196, 196);
  font-size: 16px;
  font-weight: bold;
  border: none;
  padding: 10px 35px;
  cursor: pointer;
}
.addTask__container form button:hover {
  opacity: 0.7;
}
@media(max-width: 526px){

  .addTask__container form{
    width: 100%;
    
  }
  .addTask__container{
    padding: 70px 25px;
  }
}
</style>
