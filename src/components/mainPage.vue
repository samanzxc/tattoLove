<script setup>
import { ref } from 'vue'
import addTaskPage from './addTaskPage.vue'
import myTaskPage from './myTaskPage.vue'
import infoTaskPage from './infoTaskPage.vue';

let activePage = ref('add')
</script>

<template>
    <addTaskPage v-if="activePage === 'add'"/>
    <myTaskPage  v-if="activePage === 'myTask'"/>
    <infoTaskPage  v-if="activePage === 'info'"/>
<footer class="menu">
    <button :class="{active: activePage === 'add'}"  @click="activePage = 'add'">Добавить задачу</button>
    <button :class="{active: activePage === 'myTask'}" @click="activePage = 'myTask'">Мои задачи</button>
    <button :class="{active: activePage === 'info'}" @click="activePage = 'info'">Информация</button>
</footer>
</template>

<style scoped>
.menu {
position: fixed;
left: 0;
right: 0;
bottom: 0;
height: 125px;
display: flex;
}
.menu button {
    width: 100%;
    height: 100%;
    cursor: pointer;
    background-color: var(--btn-collor);
    border: none;
    color: #fff;
    font-weight: bold;
    font-size: 17px;
    border-right: 2px #ffffff33 solid;
}
.menu button:last-child{
    border: none;
}
.menu button.active{
    background-color: var(--btn-active-color);

}
@media(max-width: 768px){
    .menu{
        height: 75px;
        
    }
    .menu button{
        font-size: 13px;
        font-weight: normal;
    }
}
</style>
