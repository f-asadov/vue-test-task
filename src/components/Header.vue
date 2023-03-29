<template>
  <div class="header">
    <div class="title">
      <h1>Товары</h1>
      <p class="tarif">{{products.length}} из 500 по тарифу Бизнес</p>
    </div>
    <div class="actions">
      <button class="button param-button">Параметры товаров</button>
      <button class="button add-button">Добавить товары</button>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    products:{
      type:Array,
      required:true
    }
  }
}

</script>

<style scoped>
.header {
  min-width: 80vw;
  height: 100px;
  padding-top: 40px;
  display: flex;
  align-items: center;
  align-content: center;
  justify-content: space-between;
}

.title {
  display: flex;
  flex-direction: column;
  gap: 40px;
  margin-left: 40px;
}

.tarif {
  font-size: 18px;
}

.actions {
  margin-right: 40px;
  display: flex;
  gap: 15px;
  margin-bottom: 25px;
}

.button {
  border: none;
  border-radius: 10px;
  height: 50px;
  width: 200px;
  color: white;
  font-size: 18px;
  cursor: pointer;
}

.param-button {
  background-color: #00b050;
}

.add-button {
  background-color: #7030a0;
}
</style>