# Интернет-магазин курсов

Проект приложения интернет-магазина курсов. Приложение разработано с учётом перечня всего функционала интернет магазина, в том числе корзина, заказы и организация профиля пользователя. README описан в формате, который по строково объясняет значение той или иной логики кода. Уровень описания проекта предполагает, что читающий является новичком. 

Реализация проекта на Heroku [Ссылка на проект](https://stark-wildwood-85340.herokuapp.com/). <br/>

---

## Оглавление документации 
- [Интернет-магазин курсов](#интернет-магазин-курсов)
  - [Оглавление документации](#оглавление-документации)
  - [Применение](#применение)
  - [Разделы](#разделы)

---

## Применение

Приложение разработано на серверной платформе Node.js с включением базы данных MongoDB, шаблонизатора Handlebars и различных middlware модулей. <br/>

Приложение выполнено по MVC-паттерну где: <br/>
- M - Model или модель. Модель представляет из себя схему, которая определяет перечень принимаемых и обрабатываемых данных. Также модель может включает в себя методы определяемые в конкретной модели. Такими методами могут быть, к примеру, перевод формата ID в базе данных MongoDB в формат ID принимаемый `Node.js` серверов. <br/>
- V - View или представления. Преставления визуализируют данные, тем самым позволяя разработчику более удобный взгляд и проверку реализации тех или иных функций и методов. <br/>
- С - Controller или контроллер. Контроллер это обработчик данных, который в зависимости от типа запроса и маршрута определяет функционал реализации. <br/>

---

Базовое понимание MVC-паттерна замыкается, на трёх блоках - модели, представления и контроллере. В свою очередь блоки имеют следующие между собой зависимости: <br/>
- Пользовательские взаимодействия с представлениями определяют работу контроллера. <br/>
- Контроллер определяет функционал обращения к модели. <br/>
- Модель предоставляет необходимые данные представлению. <br/>
Приложение же является более сложным, чем базовое понимание и поэтому включает в себя блок промежутоных обработчиков (middleware). Промежучтоные обработчики являются дополнительными обработчиками контроллеров к обращению к моделям. <br/>

Общая схема работы паттерна описана ниже: <br/>

[![0.png](https://i.postimg.cc/3wJpFsLh/0.png)](https://postimg.cc/v4kcQNF2)

Код запуска сервера: <br/>
```node
const express = require('express')

const app = express()
const PORT = process.env.PORT || 3000

app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`)
    })
```
Где: <br/>
- `app` - экземпляр функции express(). <br/>
- `PORT` - номер localhost для локального разворачивания приложения или process.env.PORT в случае запуска в режиме готового приложения. <br/>

---

## Разделы 

Подробнее о структурах приложения смотрите в разделах:
- [Вводные данные](sections.md/inputData.md). <br/>
- [Представления](sections.md/views.md). <br/>
- [Маршутизаторы](sections.md/routes.md). <br/>
- [Контроллеры](sections.md/controllers.md). <br/>
- [Промежуточные обработчики](sections.md/middleware.md). <br/>
- [Модели](sections.md/models.md). <br/>