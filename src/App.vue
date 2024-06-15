<script setup>
import headers from './components/headers.vue'
import footers from './components/footers.vue'

window.yaContextCb.push(() => {
  Ya.Context.AdvManager.render({
    blockId: 'R-A-9146296-1',
    renderTo: 'yandex_rtb_R-A-9146296-1'
  })
})
</script>

<template>
  <div class="wrapp">
    <div class="add__block">
      <!-- Yandex.RTB R-A-9146296-1 -->
      <div id="yandex_rtb_R-A-9146296-1"></div>
    </div>
    <div class="container">
      <headers />
    </div>
    <div class="add__block"></div>
  </div>
  <footers />
</template>

<style scoped>
.container {
  min-width: 1250px;
  padding: 20px;
  overflow: hidden;

  border-top: none;
  border-bottom: none;
}
.wrapp {
  display: flex;
  justify-content: center;
}
.add__block {
  width: 100%;
}
@media (max-width: 1615px) {
  .container {
    min-width: 1100px;
  }
}
@media (max-width: 1440px) {
  .container {
    min-width: 975px
  }
}
@media (max-width: 1340px) {
  .container {
    min-width: 850px;
  }
}
@media (max-width: 1240px) {
  .container {
    min-width: 640px;
  }
}
@media (max-width: 1024px) {
  .container {
    min-width: 525px;
  }
}
@media (max-width: 875px) {
  .container {
    min-width: 400px;
  }
}
@media (max-width: 670px) {
  .container {
    min-width: 325px;
  }
}
</style>
