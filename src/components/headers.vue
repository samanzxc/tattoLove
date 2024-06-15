<script setup>
import { ref, computed } from 'vue'
import popular from './popular.vue'
import serchPage from './serchPage.vue'
import allTattos from './allTatto'

window.addEventListener('DOMContentLoaded', () => {
  setTimeout(() => {
    document.querySelector('.header__body__left').classList.add('cent-left')
    document.querySelector('.header__body__right').classList.add('cent-right')
  }, 0)
})

let isSerching = ref(false)
let inputValue = ref()
let searchValue = ref()
let searchingTatto = ref()

function home() {
  isSerching.value = false
  inputValue.value = ''
}

function searhInPage() {
  searchValue.value = inputValue.value
  if (inputValue.value) {
    isSerching.value = true
  }
 searchingTatto = computed(() => {
    let search = searchValue.value.toLowerCase()
    return allTattos.filter(el => el.name.toLowerCase().includes(search) 
    || el.category.toLowerCase().includes(search) 
    || el.stw.toLowerCase().includes(search))
  })
}
</script>

<template>
  <header class="header">
    <div class="header__top">
      <div class="logo" @click="home">
        <p>Tatto<span class="blue">Love</span></p>
      </div>
      <div class="serch">
        <form action="/" @submit.prevent="searhInPage">
          <input type="search" placeholder="Введите название..." v-model="inputValue" />
          <button type="submit">найти</button>
        </form>
      </div>
    </div>
    <div v-if="!isSerching" class="header__body">
      <div class="header__body__left">
        <div class="text">
          <p>
            Ищите вдохновение для следующей татуировки? Вы попали в
            <span class="blue">нужное место!</span>
          </p>
        </div>
      </div>
      <div class="header__body__right">
        <div class="text">
          <p>
            <span class="blue">Здесь собрано</span> большое количество различных идей для
            татуировок. Просто начните искать, или выберите из популярных категорий
          </p>
        </div>
      </div>
    </div>
  </header>

  <popular v-if="!isSerching" />
  <div v-if="isSerching" class="wrapp">
    <h1 class="empty" v-if="isSerching && !searchingTatto.length">По запросу "{{ searchValue }}" ничего не найдено</h1>
  <serchPage v-if="isSerching" :searchingTatto="searchingTatto" />
</div>
</template>

<style scoped>
.header__top {
  display: flex;
  align-items: center;
  column-gap: 170px;
  margin-bottom: 100px;
}
.logo {
  font-size: 34px;
  font-weight: bold;
  cursor: pointer;
}
.serch form {
  display: flex;
  column-gap: 10px;
}
.serch form input {
  border: none;
  padding: 13px 20px;
  border-radius: 15px;
  background: rgb(240, 240, 240);
  width: 500px;
  font-size: 17px;
}
.serch form input:focus {
  outline: 2px var(--blue-collor) solid;
}

.serch form button {
  border: none;
  border-radius: 15px;
  font-size: 17px;
  width: 75px;
  cursor: pointer;
}
.serch form button:hover {
  background-color: #dfdfdf;
}
.header__body {
  display: flex;
  flex-direction: column;
  font-size: 36px;
  font-weight: 700;
  row-gap: 100px;
  margin-bottom: 300px;
}
.text {
  width: 750px;
}
.header__body__left {
  transition: 1s;
  display: flex;
  justify-content: start;
  position: relative;
  left: -1000px;
  opacity: 0;
}
.header__body__right {
  transition: 1s;
  display: flex;
  justify-content: end;
  position: relative;
  right: -1000px;
  opacity: 0;
}
.cent-left {
  transition: 1.5s;
  left: 0;
  opacity: 1;
}
.cent-right {
  transition: 1.5s;
  right: 0;
  opacity: 1;
}
.wrapp{
  min-height: 71.4dvh;
}
.empty{
  display: flex;
  justify-content: center;
  font-size: 25px;
  color: rgba(0, 0, 0, 0.349);
}
@media (max-width: 1340px) {
  .header__top{
    column-gap: 35px;
  }
  .header__body{
    font-size: 25px;
  }
}
@media (max-width: 1240px) {
  .logo{
    display: none;
  }
  .header__top{
    justify-content: center;
  }
  .serch form input{
    width: 100%;
  }
}
@media (max-width: 670px) {
  .header__body{
    font-size: 15px;
  }
  .text{
    width: 285px;
  }
}

</style>
