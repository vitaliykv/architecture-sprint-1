Задание 1:

исходный проект:

 бэк-контроллеры:
  - cards - картинки, лайки
  - user - пользователь, создание, вход

фронт:
index.js - точка входа 
App - основной компонент, использует все компоненты
ProtectedRoute - компонент, редиректит неавторизованного пользователя на вход
Main - компонент, список карточек, аватар  и инициация редактирования аватара и профиля, добавления картинки (использует Card, CurrentUserContext)
Header - компонент, хедер с входо/выход/регистрация и логотип
Footer - компонент, футер со статичным копирайтом 
Login - компонент, форма авторизации
Register - компонент, форма регистрации
Card - компонент, отображение карточки с лайками и удалением, клик по карточке (использует CurrentUserContext)
PopupWithForm - компонент-обертка, делает попал с формой и функционалом отправки и отмены
AddPlacePopup - компонент, попап добавления картинки (использует PopupWithForm)
EditAvatarPopup  - компонент, попал обновления аватара (использует PopupWithForm)
ImagePopup - компонент, попап просмотра картинки
EditProfilePopup -  компонент, попап редактирования профиля: имя и описание (использует PopupWithForm, CurrentUserContext)
InfoTooltip - компонент, успех/неудача регистрации
api - утилита, вызовы апи бэка 
auth - утилита, логин, регистрация, проверка токена
CurrentUserContext - текущий пользователь
blocks - дерево директорий со стилями 
images - картинки
vendor - шрифты



Сложность приложения низкая
Цель перехода - повышение организационной гибкости, упрощение управления кодом, повышение отказоустойчивости, более управляемое масштабирование
Команда опытная

Бизнес функции:
 - Управление профилем
 - Работа с картинками

Метод реализации - Run time - гибридный (SEO + динамика)

Подойдут оба фремворка: Module Federation и Single SPA.
Выбрал бы Module Federation - независимость разработки и развертывания и возможность использовать общие зависимости.

Межмодульное взаимодействие - Глобальное состояние 


Решение:
Три приложения:
 - Mesto (host)
 - Card - картинки, лайки
 - User - пользователь, создание, вход 


Структура:
- Mesto
 - components
  - App
  - Header
  - ProtectedRoute
  - Main
  - Footer


- Card
 - components
  - Card
  - AddPlacePopup
  - ImagePopup
  - PopupWithForm
 - utils
  - api
 

- User
 - components
  - Login
  - Register
  - EditProfilePopup
  - EditAvatarPopup
  - InfoTooltip
  - PopupWithForm
 - utils
  - api
  - auth
- contexts
 - CurrentUserContext


Задание 2:
https://drive.google.com/file/d/1STBXDIiIsD4H1IBDjMvrfhkHqrlRDtzH/view?usp=sharing
