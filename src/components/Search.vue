<template>
  <div class="search">
    <div class="categories-wrapper">
      <label for="categories" class="category-title">Категория товара</label>
      <select name="categories" id="categories" class="categories">
        <option value="">Не выбрано</option>
        <option value="">Option 1</option>
        <option value="">Option 2</option>
        <option value="">Option 3</option>
        <option value="">Option 4</option>
        <option value="">Option 5</option>
      </select>
    </div>

    <div class="search-input-wrapper">
      <input type="search" class="search-input" placeholder="Поиск товар по названию" v-on:input="(event) => this.$emit('inputChange',event)">
      <button type="submit" class="search-icon"></button>
    </div>


  </div>
</template>

<script>
export default {

}

</script>


<style scoped>
.search {
  width: 100%;
  margin-top: 40px;
  display: flex;
  align-items: start;

}


.categories-wrapper {
  display: flex;
  align-items: center;
  gap: 30px;
  width: 50%;
  margin-left: 20px;
}

.category-title {
  font-size: 18px;
}

.categories {
  height: 40px;
  border: 1px solid rgba(0, 0, 0, .1);
  outline: none;
  background-color: transparent;
  padding: 0 200px 0 0;
  margin: 0;
  cursor: pointer;
}


.search-input-wrapper {
  width: 50%;
  display: flex;
  position: relative;
  justify-content: end;
}

.search-input {
  outline: none;
  height: 40px;
  border: 1px solid rgba(0, 0, 0, .1);
  margin-right: 40px;
  width: 410px;
}

.search-icon {
  position: absolute;
  width: 20px;
  height: 20px;
  right: 50px;
  top: 10px;

}

.search-input::placeholder {
  padding-left: 10px;
  font-size: 15px;
}

.search-input[type="search"] {
  padding-right: 25px;
  background-position: right center;
  background-repeat: no-repeat;
}

.search-input[type="search"]::before {
  content: "";
  display: block;
  position: absolute;
  top: 50%;
  right: 10px;
  width: 15px;
  height: 15px;
  background-position: center;
  background-repeat: no-repeat;
  transform: translateY(-50%);
}
</style>