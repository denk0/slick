# Slick slider tutorial
## 1. Подключение
#### Через CDN (не работает в последних версиях стартеров, т.к. в них jquery включается в app.js)
- вставляем в head перед нашими главными стилями `<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/jquery.slick/1.6.0/slick.css"/>`
- и `<script type="text/javascript" src="https://cdn.jsdelivr.net/jquery.slick/1.6.0/slick.min.js"></script>` между нашим главным js файлом и jquery

#### Скачиваем файлы
- переходим в скачанный-архив.zip -> slick
- копируем файл sick.scss в src -> assets -> scss -> components
- дописываем в app.scss строку - `@import "components/slick";`
- копируем из скачанный-архив.zip -> slick файл slick.min.js в src -> assets -> js

#### Установка через bower (приветствуется)
- пишем `bower install --save slick-carousel` в корне проекта
- в файле config.yml под строкой `- "bower_components/bootstrap-sass/assets/stylesheets/bootstrap"` (тут может быть foundation) добавляем `- "bower_components/slick-carousel/slick"`
и под строкой `- "bower_components/what-input/dist/what-input.js"` добавляем `- "bower_components/slick-carousel/slick/slick.min.js"`
- в src -> assets -> scss -> app.scss добавляем `@import "slick.scss";`

## 2. Подготовка верстки
- создаем верстку <br>
 `<div class="ba-slider">`<br>
 `  <div class="ba-slide">slide 1</div>`<br>
 `  <div class="ba-slide">slide 2</div>`<br>
 `  <div class="ba-slide">slide 3</div>`<br>
 `</div>`
- если верстка будет включать классы bootstrap/foundation - ничего не сломается, т.е. верстка <br>
 `<div class="container">` <br>
 ` <div class="row ba-slider">`<br>
 `  <div class="col-md-4 ba-slide">slide 1</div>`<br>
 `  <div class="col-md-4 ba-slide">slide 2</div>`<br>
 `  <div class="col-md-4 ba-slide">slide 3</div>`<br>
 ` </div>`<br>
 `</div>`<br>
 тоже подходит.
- важно чтобы `.ba-slide` был прямым ребенком `.ba-slider`!
  т.е. <br>
  `<div class="container ba-slider">`<br>
    `<div class="row">`<br>
      `<div class="col-md-4 ba-slide">slide 1</div>`<br>
      `<div class="col-md-4 ba-slide">slide 2</div>`<br>
      `<div class="col-md-4 ba-slide">slide 3</div>`<br>
    `</div>`<br>
 `</div>`<br>
 не будет работать
 
## 3. Инициализация слайдера
- Добавляем `$(window).on('load', function() {
		$('.ba-slider').slick();
	});`
  в src -> assets -> js -> app.js
- Конструкция `$(window).on('load', ...` нужна для инициализации слайдера только после того, как все элементы страницы загрузились.
 
## 4. Добавляем свои настройки по [документации](http://kenwheeler.github.io/slick/) 
