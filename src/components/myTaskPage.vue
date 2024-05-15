<script setup>
import { ref } from 'vue'
import { task } from './globarVar'
import { finishTask } from './globarVar'



function startTimer(item) {
  item.timerActive = !item.timerActive

  if (item.timerActive) {
    item.timerInterval = setInterval(() => {
      item.timer[0]++
      if (item.timer[0] >= 99) {
        item.timer[0] = 0
        item.timer[1]++
      }
      if (item.timer[1] >= 59) {
        item.timer[1] = 0
        item.timer[2]++
      }
    }, 10)
  } else {
    clearInterval(item.timerInterval)
  }
  checkActive(event)
  localStorage.setItem('taskItem', JSON.stringify(task.value))
}

function endTask(item){
    clearInterval(item.timerInterval)
    finishTask.value.push(item)
    deletTask(item)
    localStorage.setItem('finishTaskItem', JSON.stringify(finishTask.value))
}

function deletTask(item) {
  task.value = task.value.filter((el) => el.id != item.id)
  localStorage.setItem('taskItem', JSON.stringify(task.value))
}

function checkActive(event){
  if (event.target.classList.contains('btn')) {
    event.target.classList.toggle('active')
  }
}
</script>

<template>
  <div class="myTask">
    <div class="wrapp">
      <p class="myTask__text">Список Задач</p>
      <div class="myTask__wrapp">
        <div class="empty" v-if="!task.length"><h1>Нет активных задач</h1></div>
        <div class="task__block" v-for="(item, index) in task" :key="index">
          <div class="task">
            <p class="task__text">{{ item.text }}</p>
            <div class="task__btn">
              <img @click="startTimer(item)" class="btn" :src="item.timerActive ? 'https://www.pngarts.com/files/2/Pause-PNG-Picture.png' : 'https://static.tildacdn.com/tild6363-6534-4562-a562-336133346563/play-vector-icon.png'"/>

                <img @click="endTask(item)" class="btn" src="https://www.svgrepo.com/show/48420/racing-flag.svg" alt="" />

                <img @click="deletTask(item)" class="btn" src="https://cdn2.iconfinder.com/data/icons/e-commerce-line-10-1/1024/remove10-1024.png" alt=""/>
            </div>
          </div>
          <div class="timer">
            <span v-show="item.timer[2] < 10">0</span>{{ item.timer[2] }}:<span
              v-show="item.timer[1] < 10"
              >0</span
            >{{ item.timer[1] }}:<span v-show="item.timer[0] < 10">0</span>{{ item.timer[0] }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.myTask {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding-top: 30px;
}
.myTask__text {
  font-weight: bold;
  font-size: 35px;
  margin-bottom: 20px;
}
.myTask__wrapp {
  border-radius: 10px;
  background: rgb(90, 54, 134);
  width: 750px;
  padding: 25px 20px;
  display: flex;
  flex-direction: column;
  row-gap: 30px;
  max-height: 620px;
  overflow: auto;
}
.task__block {
  display: flex;
  justify-content: space-between;
  align-items: center;
  column-gap: 15px;
  color: #ffffffcb;
}
.task {
  border-radius: 10px;
  padding: 10px;
  display: flex;
  align-items: start;
  justify-content: space-between;
  width: 100%;
  max-width: 750px;
  word-break: break-all;
  background-color: black;
  font-weight: bold;
  font-size: 18px;
}
.task__btn {
  margin-left: 15px;
  display: flex;
  column-gap: 7px;
}
.task__btn img{
  height: 35px;
  width: 35px;
  background-color: #fff;
  padding: 5px;
  border-radius: 10px;
  cursor: pointer;
}
.task__btn img:hover {
  opacity: 0.7;
}
.timer {
  font-size: 23px;
  font-weight: bold;
  min-width: 100px;
  max-width: 100px;

}
.empty {
  text-align: center;
  color: #ffffff3a;
}
.task__btn .active{
  background-color: #a8a8a8;
}
@media(max-width: 768px){
  .myTask__wrapp{
    width: 600px;
  }
}
@media(max-width: 615px){
  .myTask__wrapp{
    width: 480px;
  }
}
@media(max-width: 514px){
  .myTask__wrapp{
    width: 400px;
  }
  .task__text{
    font-size: 13px;
  }
  .task__btn img {
    height: 30px;
    width: 30px;
  }
  .timer{
    font-size: 19px;
  }
}
@media(max-width: 415px){
  .myTask__wrapp{
    max-height: 480px;
    width: 350px;
  }
}
</style>
