# 📚 Калькулятор 📚

Источник: видео "Speed Coding | HTML, CSS, JS - Calculator" 
https://vk.com/im/convo/19460369?entrypoint=list_all&z=video-101965347_456276133%2F98c1eac7213a7f330f

![2025-01-04_14-36-57](https://github.com/user-attachments/assets/874c4091-e8ff-44cf-aadc-61b759168b0e)


https://github.com/user-attachments/assets/5c6603c7-eeb0-4132-b9ba-92a38d4290db



1. создаем создаем файлы index.html, style.css (в папке css), script.js (в папке js) в папке проекта.

2. в файле index.html готовим шаблон

```html
<!-- Сообщаем браузеру, как стоит обрабатывать эту страницу -->
<!DOCTYPE html>
<!-- Оболочка документа, указываем язык содержимого -->
<html lang="ru">
<!-- Заголовок страницы, контейнер для других важных данных (не отображается) -->
<head>
    <!-- Заголовок страницы в браузере -->
    <title></title>
    <!-- Подключаем CSS -->
    <link rel="stylesheet" href="css/style.css">
    <!-- Кодировка страницы -->
    <meta charset="utf-8">
    <!-- Адаптив -->
    <meta name="viewport" content="width=device-width">
</head>
<!-- Отображаемое тело страницы -->
<body>
<!-- Оболочка для демонстрации -->
<div class="wrapper">
    <!-- Контент -->
   
    <!-- Подключаем файл JS скриптов -->
    <script src="js/script.js"></script>
</div>
</body>
</html>
```

3. в файле style.css вставляем шаблон

```css
/* Обнуление */
*,*:before,*:after{
   padding: 0;
   margin: 0;
   border: 0;
   box-sizing: border-box;
}
/* Стили для демонстрации */
html,body{
   height: 100%;
   background-color: #333;
   font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
   color: #fff;
   font-size: 25px;
}
.wrapper{
   height: 100%;
   padding: 50px;
}
/* Основные стили */
```

4. в файле index.html называем проект в разделе head

```html
<title>Калькулятор</title>
```

5. в файле index.html создаем таблицу в разделе body

```html
<div class="main">
    <form name="form">
        <input class="textview">
    </form>
    <table>
        <tr>
            <td><input type="button" value="C"></td>
            <td><input type="button" value="<"></td>
            <td><input type="button" value="/"></td>
            <td><input type="button" value="x"></td>
        </tr>
        <tr>
            <td><input type="button" value="7"></td>
            <td><input type="button" value="8"></td>
            <td><input type="button" value="9"></td>
            <td><input type="button" value="-"></td>
        </tr>
        <tr>
            <td><input type="button" value="4"></td>
            <td><input type="button" value="5"></td>
            <td><input type="button" value="6"></td>
            <td><input type="button" value="+"></td>
        </tr>
        <tr>
            <td><input type="button" value="1"></td>
            <td><input type="button" value="2"></td>
            <td><input type="button" value="3"></td>
            <td><input type="button" value="="></td>
        </tr>
        <tr>
            <td><input type="button" value="0"></td>
            <td><input type="button" value="."></td>
        </tr>
    </table>
</div>
```

6. в файле style.css стилизуем кнопки

```css
.button{
    width: 50px;
    height: 50px;
    font-size: 25px;
    margin: 2px;
    cursor: pointer;
    background: #607d8b;
    border: none;
    color: white;
}
```

7. в файле style.css стилизуем строку для просмотра результата

```css
.textview{
    width: 217px;
    margin: 5px;
    font-size: 25px;
    padding: 5px;
    border: none;
    color: #607d8b;
}
```

8. в файле script.js чтобы числовое поле выводило результат после нажатий кнопок

```js
function insert(num){
    document.form.textview.value = document.form.textview.value+num
}
```

9. в файле index.html - чтобы кнопки реагировали на клик и выдавали нужный результат

добавляем name
```html
<input class="textview" name="textview">
```
добавляем onclick="" и class
```html
<td><input class="button" type="button" value="/" onclick="insert('/')"></td>
<td><input class="button" type="button" value="x" onclick="insert('*')"></td>
<td><input class="button" type="button" value="7" onclick="insert(7)"></td>
<td><input class="button" type="button" value="8" onclick="insert(8)"></td>
<td><input class="button" type="button" value="9" onclick="insert(9)"></td>
<td><input class="button" type="button" value="-" onclick="insert('-')"></td>
<td><input class="button" type="button" value="4" onclick="insert(4)"></td>
<td><input class="button" type="button" value="5" onclick="insert(5)"></td>
<td><input class="button" type="button" value="6" onclick="insert(6)"></td>
<td><input class="button" type="button" value="+" onclick="insert('+')"></td>
<td><input class="button" type="button" value="1" onclick="insert(1)"></td>
<td><input class="button" type="button" value="2" onclick="insert(2)"></td>
<td><input class="button" type="button" value="3" onclick="insert(3)"></td>
<td><input class="button" type="button" value="." onclick="insert('.')"></td>
```

10. чтобы работала кнопка '='

index.html
```html
<td><input class="button" type="button" value="=" onclick="equal()"></td>
```
script.js
```js
function equal(){
    var exp = document.form.textview.value;
    if(exp){
        document.form.textview.value = eval(exp)
    }
}
```

11. чтобы работала кнопка "C" - "clear" (очистка поля)

index.html - добавляем class и onclick
```html
<td><input class="button" type="button" value="C" onclick="clean()"></td>
```
script.js
```js
function clean(){
    document.form.textview.value = "";
}
```

12. чтобы работала кнопка назад, отмены последнего действия

index.html - добавляем class и onclick
```html
<td><input class="button" type="button" value="<" onclick="back()"></td>
```
script.js
```js
function back(){
    var exp = document.form.textview.value;
    document.form.textview.value = exp.substring(0,exp.length-1);
}
```

13. в index.html - изменяем кнопку "0" - добавляем class и onclick, colspan, style

```html
<td colspan="2"><input class="button" style="width:106px" type="button" value="0" onclick="insert(0)"></td>
```

14. в index.html - изменяем кнопку "=" - добавляем colspan, style

```html
<td rowspan="5"><input class="button" style="height: 106px" type="button" value="=" onclick="equal()"></td>
```

15. style.css - стилизуем меню

```css
.main{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

16. стилизуем бэкграунд

index.html добавляем новый класс
```html
<div class="bg"></div>
```
style.css
```css
.bg{
    background: linear-gradient(to right, #e91e63, #3f51b5);
    height: 100%;
}
```

# Итог

1. index.html

```html
<!-- Сообщаем браузеру, как стоит обрабатывать эту страницу -->
<!DOCTYPE html>
<!-- Оболочка документа, указываем язык содержимого -->
<html lang="ru">
<!-- Заголовок страницы, контейнер для других важных данных (не отображается) -->
<head>
    <!-- Заголовок страницы в браузере -->
    <title>Калькулятор</title>
    <!-- Подключаем CSS -->
    <link rel="stylesheet" href="css/style.css">
    <!-- Кодировка страницы -->
    <meta charset="utf-8">
    <!-- Адаптив -->
    <meta name="viewport" content="width=device-width">
</head>
<!-- Отображаемое тело страницы -->
<body>
<!-- Оболочка для демонстрации -->
<div class="wrapper">
    <!-- Контент -->
    <div class="bg"></div>
    <div class="main">
        <form name="form">
            <input class="textview" name="textview">
        </form>
        <table>
            <tr>
                <td><input class="button" type="button" value="C" onclick="clean()"></td>
                <td><input class="button" type="button" value="<" onclick="back()"></td>
                <td><input class="button" type="button" value="/" onclick="insert('/')"></td>
                <td><input class="button" type="button" value="x" onclick="insert('*')"></td>
            </tr>
            <tr>
                <td><input class="button" type="button" value="7" onclick="insert(7)"></td>
                <td><input class="button" type="button" value="8" onclick="insert(8)"></td>
                <td><input class="button" type="button" value="9" onclick="insert(9)"></td>
                <td><input class="button" type="button" value="-" onclick="insert('-')"></td>
            </tr>
            <tr>
                <td><input class="button" type="button" value="4" onclick="insert(4)"></td>
                <td><input class="button" type="button" value="5" onclick="insert(5)"></td>
                <td><input class="button" type="button" value="6" onclick="insert(6)"></td>
                <td><input class="button" type="button" value="+" onclick="insert('+')"></td>
            </tr>
            <tr>
                <td><input class="button" type="button" value="1" onclick="insert(1)"></td>
                <td><input class="button" type="button" value="2" onclick="insert(2)"></td>
                <td><input class="button" type="button" value="3" onclick="insert(3)"></td>
                <td rowspan="5"><input class="button" style="height: 106px" type="button" value="=" onclick="equal()"></td>
            </tr>
            <tr>
                <td colspan="2"><input class="button" style="width:106px" type="button" value="0" onclick="insert(0)"></td>
                <td><input class="button" type="button" value="." onclick="insert('.')"></td>
            </tr>
        </table>
    </div>
    <!-- Подключаем файл JS скриптов -->
    <script src="js/script.js"></script>
</div>
</body>
</html>
```

![2025-01-04_14-34-29](https://github.com/user-attachments/assets/d5f9d2ca-d6b4-47af-a265-cc09ad76ba45)
![2025-01-04_14-34-44](https://github.com/user-attachments/assets/977ec1cb-908e-42d3-bd90-0df77b72c2ad)


2. style.css

```css
/* Обнуление */
*,*:before,*:after{
    padding: 0;
    margin: 0;
    border: 0;
    box-sizing: border-box;
}
/* Стили для демонстрации */
html,body{
    height: 100%;
    background-color: #333;
    font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
    color: #fff;
    font-size: 25px;
}
.wrapper{
    height: 100%;
    padding: 50px;
}
/* Основные стили */

.button{
    width: 50px;
    height: 50px;
    font-size: 25px;
    margin: 2px;
    cursor: pointer;
    background: #607d8b;
    border: none;
    color: white;
}
.textview{
    width: 217px;
    margin: 5px;
    font-size: 25px;
    padding: 5px;
    border: none;
    color: #607d8b;
}
.main{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
.bg{
    background: linear-gradient(to right, #e91e63, #3f51b5);
    height: 100%;
}
```

![2025-01-04_14-35-06](https://github.com/user-attachments/assets/6d7e1ffe-2b26-40c4-b081-bd46e5e948d6)


3. script.js

```js
function insert(num){
    document.form.textview.value = document.form.textview.value+num
}
function equal(){
    var exp = document.form.textview.value;
    if(exp){
        document.form.textview.value = eval(exp)
    }
}
function clean(){
    document.form.textview.value = "";
}
function back(){
    var exp = document.form.textview.value;
    document.form.textview.value = exp.substring(0,exp.length-1);
}
```

![2025-01-04_14-35-31](https://github.com/user-attachments/assets/199eda61-ddb6-43cc-9fc0-a0d54e0a953d)
