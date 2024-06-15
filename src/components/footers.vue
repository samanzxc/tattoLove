<template>
  <footer>
    <div class="logo" @click="home">
      <b>Tatto<span class="blue">Love</span></b>
    </div>
    <p>Все права защищены ©️</p>
  </footer>
</template>

<style scoped>
footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 60px;
  background-color: #e6e6e6;
  padding: 0 50px;
}
footer p {
  color: rgba(0, 0, 0, 0.274);
  font-size: 14px;
}
</style>
