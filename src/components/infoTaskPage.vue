<script setup>
import { ref } from 'vue'
import { finishTask } from './globarVar'

if (JSON.parse(localStorage.getItem('finishTaskItem'))) {
  finishTask.value = JSON.parse(localStorage.getItem('finishTaskItem'))
}

function deletTask(item) {
  finishTask.value = finishTask.value.filter((el) => el.id != item.id)
  localStorage.setItem('finishTaskItem', JSON.stringify(finishTask.value))
}

const date = new Date
let day = date.getDate()
let month = date.getMonth()+1
let yers = date.getFullYear()
</script>

<template>
  <div class="myTask">
    <div class="wrapp">
      <p class="myTask__text">Информация о завершённых задачах</p>
      <div class="myTask__wrapp" v-if="finishTask.length">
        <div class="task__block" v-for="(item, index) in finishTask" :key="index">
          <div class="task">
            <div class="wrapps">
              <p class="task__text">{{ item.text }}</p>
              <div class="task__btn">
                <button @click="deletTask(item)">
                  <img
                    src="https://cdn2.iconfinder.com/data/icons/e-commerce-line-10-1/1024/remove10-1024.png"
                    alt=""
                  />
                </button>
              </div>
            </div>
            <div class="timer">
              <div class="wps">
                <p>Выполнено за -</p>
                <span v-show="item.timer[2] < 10">0</span>{{ item.timer[2] }}:<span
                  v-show="item.timer[1] < 10"
                  >0</span
                >{{ item.timer[1] }}:<span v-show="item.timer[0] < 10">0</span>{{ item.timer[0] }}
              </div>
              <span class="date">{{day}}.{{month}}.{{yers}}</span>
            </div>
          </div>
        </div>
      </div>
      <div v-else class="empty">Выполненых задач не найдено</div>
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
.wps {
  display: flex;
  align-items: center;
}
.myTask__wrapp {
  border-radius: 10px;
  background: rgb(90, 54, 134);
  width: 750px;
  padding: 25px 20px;
  display: flex;
  flex-direction: column;
  row-gap: 30px;
  max-height: 650px;
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
  flex-direction: column;
  align-items: start;
  justify-content: space-between;
  width: 100%;
  max-width: 750px;
  word-break: break-all;
  background-color: black;
  font-weight: bold;
  font-size: 18px;
}
.wrapps {
  width: 100%;
  display: flex;
  align-items: start;
  justify-content: space-between;
}
.task__btn {
  margin-left: 15px;
  display: flex;
  column-gap: 7px;
}
.task__btn button {
  border: none;
  background-color: #fff;
  height: 35px;
  width: 35px;
  font-weight: bold;
  font-size: 10px;
  border-radius: 10px;
  cursor: pointer;
}
.task__btn button:hover {
  opacity: 0.7;
}
.task__btn button img {
  width: 20px;
  height: 20px;
}
.timer {
  width: 100%;
  font-size: 23px;
  font-weight: bold;
  margin-top: 25px;
  display: flex;
  align-items: end;
  justify-content: space-between;
}
.timer p {
  font-size: 18px;
  color: #ffffffa2;
  margin-right: 5px;
}
.timer .date {
  color: rgba(255, 255, 255, 0.43);
  font-size: 12px;
}

.task__btn .active {
  background-color: #a8a8a8;
}
.empty{
    position: relative;
    top: 150px;
    display: flex;
    justify-content: center;
    font-size: 35px;
    font-weight: bold;
    color: rgba(0, 0, 0, 0.171);
}
.wrapp{
  display: flex;
  flex-direction: column;
  align-items: center;
}
@media(max-width: 674px){
  .myTask__text{
    font-size: 21px;
    text-align: center;
  }
  .empty{
    font-size: 20px;
    text-align: center;
  }
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
  .wps p{
    font-size: 12px;
  }
  .timer{
    font-size: 15px;
  }
  .timer .date{
    font-size: 10px;
  }
}
</style>
