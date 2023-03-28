<template>
  <div class="main">
    <div class="header">
      <div class="title">
        <h1>Товары</h1>
        <p class="tarif">7 из 500 по тарифу Бизнес</p>
      </div>
      <div class="actions">
        <button class="button param-button">Параметры товаров</button>
        <button class="button add-button">Добавить товары</button>
      </div>
    </div>
    <div class="search">
      <div class="test">
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
        <input type="search" class="search-input" placeholder="Поиск товар по названию">
        <button type="submit" class="search-icon"></button>
      </div>


    </div>

    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Категория</th>
          <th>Название</th>
          <th>Сумма</th>
          <th></th> <!-- заголовок для столбца с иконкой удаления -->
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>категория 1</td>
          <td>название 1</td>
          <td>1000 руб.</td>
          <td><i class="fa fa-trash"></i></td> <!-- иконка удаления -->
        </tr>
        <tr>
          <td>2</td>
          <td>категория 2</td>
          <td>название 2</td>
          <td>2000 руб.</td>
          <td><i class="fa fa-trash"></i></td>
        </tr>
        <!-- добавьте дополнительные строки при необходимости -->
      </tbody>
    </table>
  </div>
</template>

<script>
console.log('asdasda');
</script>

<style>

table {
  border-collapse: collapse;
  width: 97%;
  
  margin: auto;
}

thead th {
  background-color: #f2f2f2;
  font-weight: bold;
  text-align: left;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}

tbody td {
  padding: 10px;
}



tbody td:last-child {
  border-bottom: none;
}

.fa-trash {
  background-image: url('https://cdn-icons-png.flaticon.com/512/4662/4662651.png');
  background-repeat: no-repeat;
  background-size: 20px 20px;
  display: inline-block;
  width: 20px;
  height: 20px;
  margin: 0 auto;
  cursor: pointer;
}
tr:not(:last-child) td{
  border-bottom:1px solid rgba(0, 0, 0, .3)
}

tr:last-child td{
  
  border-bottom:none
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
  /* border: 1px solid red; */
  width: 20px;
  height: 20px;
  right: 50px;
  top: 10px;
  background-image: url('../img/search-icon-grey.jpg');
}


.search-input::placeholder {
  padding-left: 10px;
  font-size: 15px;
}

.search-input[type="search"] {
  padding-right: 25px;
  /* добавляем отступ для места под значок поиска */
  background-image: url("https://www.iconspng.com/images/simple-grey-search-icon.jpg");
  /* путь к изображению значка поиска */
  background-position: right center;
  /* позиция изображения внутри поля */
  background-repeat: no-repeat;
  /* запрещаем повторять изображение */
}

.search-input[type="search"]::before {
  content: "";
  /* пустое содержимое элемента */
  display: block;
  position: absolute;
  top: 50%;
  right: 10px;
  width: 15px;
  height: 15px;
  background-image: url("https://www.iconspng.com/images/simple-grey-search-icon.jpg");
  /* путь к изображению значка поиска */
  background-position: center;
  background-repeat: no-repeat;
  transform: translateY(-50%);
  /* смещаем элемент на половину его высоты */
}

.test {
  display: flex;
  align-items: center;
  gap: 30px;
  width: 50%;
  margin-left: 20px;
}

.search {
  width: 100%;
  margin-top: 40px;
  display: flex;
  align-items: start;
 
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

.category-title {
  font-size: 18px;
}

.tarif {
  font-size: 18px;
}

.header {
  min-width: 80vw;
  ;
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

.actions {
  /* border:1px solid rgb(255, 51, 0); */
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

*,
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Nunito Sans', sans-serif;
}

body {
  display: flex;
  height: 100vh;
  justify-content: center;
  align-items: center;
}

.main {
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 20px;
  height: 60vh;
  
}
</style>