<script setup>
import allTattos from './allTatto'

const props = defineProps({
  searchingTatto: Array
})
</script>

<template>
  <div class="wrapp">
    <div class="tatto" v-for="(tatto, index) in props.searchingTatto" :key="index">
      <div class="info">
        <p class="title">{{ tatto.name }}</p>
        <div class="teg">{{ tatto.category }}</div>
      </div>
      <p class="desc">{{ tatto.desc }}</p>
      <img :src="tatto.url" alt="" />
    </div>
  </div>
</template>

<style scoped>
.wrapp {
  display: flex;
  flex-direction: column;
  row-gap: 150px;
}
.tatto {
  display: flex;
  align-items: start;
  flex-direction: column;
  padding: 20px;
  box-shadow: 0 0 10px 1px rgba(0, 0, 0, 0.062);
  row-gap: 15px;
  border-radius: 10px;
}
.tatto img {
  width: 800px;
  height: 850px;
  border-radius: 5px;
}
.title {
  font-weight: bold;
  font-size: 25px;
}

.desc {
  font-size: 30px;
  color: rgba(0, 0, 0, 0.767);
  max-width: 850px;
}
.info {
  display: flex;
  align-items: center;
  column-gap: 15px;
}
.teg {
  background-color: var(--teg-color);
  padding: 10px;
  border-radius: 15px;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
}
@media (max-width: 1340px) {
  .tatto img {
    width: 550px;
    height: 650px;
  }
}
@media (max-width: 1240px) {
  .tatto img {
    width: 400px;
    height: 500px;
  }
  .title {
    font-size: 17px;
  }
  .teg {
    font-size: 14px;
  }
  .desc {
    font-size: 20px;
  }
}
@media (max-width: 875px) {
  .tatto img {
    width: 300px;
    height: 400px;
  }
}
@media (max-width: 670px) {
  .tatto img {
    width: 250px;
    height: 350px;
  }
  .title {
    font-size: 15px;
  }
  .teg {
    font-size: 12px;
  }
  .desc {
    font-size: 18px;
  }
}
</style>
