# 20th Century - Шаблон для быстрого старта верстки почтовых рассылок

![](http://s020.radikal.ru/i716/1506/2c/4116d3c6c9e6.jpg)

## Как начать

У вас должны быть установлены:

- [ruby](https://www.ruby-lang.org/ru/downloads/)
- [nodejs и npm](https://nodejs.org/)
- [gulp](http://gulpjs.com/)

Далее выполняем:

```
sudo npm i
gulp build
```

После выкачивания всех зависимостей проекта и успешной первичной сборки, запустите задачу `gulp` и можете приступать к верстке.

Также для удобства можете пользоваться [этой таблицей](https://www.campaignmonitor.com/css/).

## Что включено?

- компиляция sass в css
- автоматическое проставление inline-стилей
- сжатие изображений и HTML-кода
- отправка готового макета на указанный email

### Общий принцип работы

Все стили расположены в папке `src/sass`. В главном файле **main.sass** происходит импорт всех нужных модулей. Далее стили компилируются в CSS и кладутся в папку `src/css`. Оттуда потом сборщик берет все стили и производит внедрение их в HTML-файл, после чего кладет готовый результат в папку `dist`.

Все исходные изображения хранятся в `src/img`. При каждом изменении содержимого папки Gulp очищает `dist/img` и кладет туда сжатые изображения.

### Примеры кода

index.html:

```
<html>
<head>
	<style>
		p { color: red; }
	</style> 
	<link rel="stylesheet" href="css/main.css">
</head>
<body>
	<p>Test</p>
</body>
</html>
```

style.css:

```
p {
	text-decoration: underline;
}
```

Результат:

```
<html>
	<head>
	</head>
	<body>
		<p style="color: red; text-decoration: underline;">Test</p>
	</body>
</html>
```

### Тестирование

Для отправки писем используется задача `gulp test`. Чтобы она работала, вам сначала нужно будет произвести некоторые настройки.

1. Зарегистрируйтесь на сайте [MailGun.com](http://www.mailgun.com/).
2. Вам выдадут бесплатный домен, данные которого необходимо будет добавить в gulpfile.js (войдя под своей учетной записью, подсмотрите нужные параметры на [странице с примерами](https://documentation.mailgun.com/api-sending.html#examples)).

На каждый месяц у вас будет лимит - 10.000 писем. Дополнительно ознакомиться с правилами вы [можете здесь](http://www.mailgun.com/pricing).

## Материалы в помощь

### Самое важное

- мысленно вернитесь в конец прошлого века
- верстка только таблицами
- забыть про скрипты

### Отступы

- у каждой таблицы обнулять атрибуты cellpadding и cellspacing, а также коллапсировать таблицу
- однопиксельный прозрачный .gif для отступов (например, img src="blank.gif" style="width:20px;")
- не использовать абсолютное позиционирование

### Форматирование текста

- оформление задавать inline для каждого элемента
- о теге **font** нужно забыть вовсе
- font-family, font-size и color — в формате #xxxxxx или фактическом, например red
- можно использовать теги **b, i, u, strong** и др.

### Гиперссылки

- значение _blank атрибута target

### Изображения

- для всех изображений установить ширину и высоту равной фактической (через атрибуты или в стилях)
- если картинка - ссылка, то убираем border (через стили или напрямую) и text-decoration: none;

### Фон

- фон в виде цвета можно указывать для тела документа, таблицы и ее ячеек
- фон в виде картинок - нельзя

### Статьи

- [Верстка почтовых рассылок](http://habrahabr.ru/post/112163/)
- [Верстка рассылок — что мы имеем?](http://habrahabr.ru/post/157309/)
- [How-to: Правила вёрстки email-писем](http://habrahabr.ru/company/pechkin/blog/255819/)
- [Верстка почтовых рассылок: разбор полетов](http://habrahabr.ru/post/114234/)
- [Основы профессиональной верстки электронных писем](http://habrahabr.ru/post/180013/)
- [Верстка писем, набор сниппетов](http://habrahabr.ru/post/193430/)
- [5 правил верстки email-писем от Печкина](http://habrahabr.ru/company/pechkin/blog/182964/)
- [Верстка писем и email рассылок. Немного магии Gmail](http://habrahabr.ru/post/193790/)
- [Верстка email рассылок от А до Я для чайников](http://habrahabr.ru/post/252279/)
- [Mastering HTML Email (5 posts)](http://dev.tutsplus.com/series/mastering-html-email--webdesign-17696?view=grid)
- [Creating a Simple Responsive HTML Email](http://dev.tutsplus.com/articles/creating-a-simple-responsive-html-email--webdesign-12978)
- Вёрстка адаптивных email-писем (подробное руководство): [часть 1](http://habrahabr.ru/company/pechkin/blog/256853/), [часть 2](http://habrahabr.ru/company/pechkin/blog/257397/)
- [Things I've Learned About Building & Coding HTML Email Templates](http://www.leemunroe.com/building-html-email/)
- [Creating a Future-Proof Responsive Email Without Media Queries](http://webdesign.tutsplus.com/tutorials/creating-a-future-proof-responsive-email-without-media-queries--cms-23919)
- [Responsive Email Patterns](http://responsiveemailpatterns.com/)
- [A Guide for SVG Support in Email](https://css-tricks.com/a-guide-on-svg-support-in-email/)
- [Вёрстка писем: 60 полезных ресурсов, руководств и исследований](http://habrahabr.ru/company/pechkin/blog/273677/)

### Инструменты

- [HTML Email Boilerplate](http://htmlemailboilerplate.com/)
- [Free Email Templates](http://www.campaignmonitor.com/templates/)
- [Responsive HTML emails](http://zurb.com/ink/)

## Контакты

Если у вас имеются какие-либо вопросы или пожелания, пишите письма на [nikbelikov@me.com](mailto:nikbelikov@me.com) или воспользуйтесь [твиттером](https://twitter.com/_nikbelikov).

## Лицензия

Copyright (c) 2015 [nikbelikov.ru](http://nikbelikov.ru/)

Данная лицензия разрешает лицам, получившим копию данного программного обеспечения и сопутствующей документации (в дальнейшем именуемыми «Программное Обеспечение»), безвозмездно использовать Программное Обеспечение без ограничений, включая неограниченное право на использование, копирование, изменение, добавление, публикацию, распространение, сублицензирование и/или продажу копий Программного Обеспечения, также как и лицам, которым предоставляется данное Программное Обеспечение, при соблюдении следующих условий:

Указанное выше уведомление об авторском праве и данные условия должны быть включены во все копии или значимые части данного Программного Обеспечения.

ДАННОЕ ПРОГРАММНОЕ ОБЕСПЕЧЕНИЕ ПРЕДОСТАВЛЯЕТСЯ «КАК ЕСТЬ», БЕЗ КАКИХ-ЛИБО ГАРАНТИЙ, ЯВНО ВЫРАЖЕННЫХ ИЛИ ПОДРАЗУМЕВАЕМЫХ, ВКЛЮЧАЯ, НО НЕ ОГРАНИЧИВАЯСЬ ГАРАНТИЯМИ ТОВАРНОЙ ПРИГОДНОСТИ, СООТВЕТСТВИЯ ПО ЕГО КОНКРЕТНОМУ НАЗНАЧЕНИЮ И ОТСУТСТВИЯ НАРУШЕНИЙ ПРАВ. НИ В КАКОМ СЛУЧАЕ АВТОРЫ ИЛИ ПРАВООБЛАДАТЕЛИ НЕ НЕСУТ ОТВЕТСТВЕННОСТИ ПО ИСКАМ О ВОЗМЕЩЕНИИ УЩЕРБА, УБЫТКОВ ИЛИ ДРУГИХ ТРЕБОВАНИЙ ПО ДЕЙСТВУЮЩИМ КОНТРАКТАМ, ДЕЛИКТАМ ИЛИ ИНОМУ, ВОЗНИКШИМ ИЗ, ИМЕЮЩИМ ПРИЧИНОЙ ИЛИ СВЯЗАННЫМ С ПРОГРАММНЫМ ОБЕСПЕЧЕНИЕМ ИЛИ ИСПОЛЬЗОВАНИЕМ ПРОГРАММНОГО ОБЕСПЕЧЕНИЯ ИЛИ ИНЫМИ ДЕЙСТВИЯМИ С ПРОГРАММНЫМ ОБЕСПЕЧЕНИЕМ.