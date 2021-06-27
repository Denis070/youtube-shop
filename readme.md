# YouTube Shop

Этот проект - обобщение двух сериалов вышедших на моем [канале](https://www.youtube.com/channel/UCf6kozNejHoQuFhBDB8cfxA)

- [Видео из картинок и текста c FFmpeg](https://www.youtube.com/watch?v=0XgvQkIksdA&list=PLWVnIRD69wY5rFHFPjD2CVdShIvfqT2MH)
- [Работа с YouTube API](https://www.youtube.com/watch?v=upasLEUGrH4&list=PLWVnIRD69wY7DoPeDvwl2ndrfZMN8cARl)

Здесь же готовый (условно, полуфабрикат) рабочий проект, который может:

- Парсить товарные карточки магазинов. 
- Вытаскивать статичный контент (картинки, цену, заголовки, описания).
- Генерить из статичного контента видео ролики с анимированными картинками,
наложенными текстами заголовков и бесплатной музыкой.
~~- В автоматическом режиме выкладывать видео на YouTube через YouTube API.~~
~~- Добавлять к видео на YouTube заголовки, теги, описания со ссылками на товар (корзину, рефку и т.п.)~~
~~- Добавлять топовый закрепленный коммент к ролику~~
YouTube запретил публикацю видео в паблик через API для приложений без аппрува в июле 2020 года. 
Т.к. для такого приложения шансы пройти модерацию представляются маловероятными, то полного автомата,
к сож. уже не получится (а раньше было можно).

**Поэтому задача проекта теперь заканчивается на этапе генерации видео и описания к видео.**

### Видео Пояснялка

[Python, парсинг сайта  интернет-магазина | Youtube Shop ч. 1](https://youtu.be/xMENimADrzA)
[Tkinter - графический интерфейс для Python | Youtube Shop ч. 2](https://www.youtube.com/watch?v=y3ATgiiDwuk)


## Что дальше?

Поднять venv. Создать приложение в Google Cloud Platform. Получить API Key и OAuth Client ID. 
Запросить и сохранить токены под тот канал куда будет загружаться видео. 

В принципе весь проект можно упаковать в PyInstaller или в Докер и сделать законченное решение, 
но здесь такой задачи не стояло.

## Помощь и поддержка

:blush: Если что-то не получается и в моих видосиках вдруг нет ответа, то пишите в комменты к любому моему видео. 
Стараюсь отвечать всем, но ничего не обещаю ;)

:moneybag: Нужно что-то доделать/переделать под конкретное ТЗ ? Все возможно, особенно если задача интересная 
и/или бюджет достойный. Также пишите в тг/ют.

## Спасибы

Хочешь сказать спасибо - подпишись, лайкни, напиши коммент.

- [Канал на YouTube](https://www.youtube.com/channel/UCf6kozNejHoQuFhBDB8cfxA)
- [Канал в Telegram](https://t.me/azzraelru)
- [Сайт](https://azzrael.ru)

## По парсингу
Для парсинга использую простую связку requests + lxml xpath
- https://docs.python-requests.org/en/master/user/quickstart/#make-a-request
- https://lxml.de/lxmlhtml.html
- https://www.guru99.com/xpath-selenium.html

!!! C lxml могут быть сложности с установкой
Для Win 10 Python 3.8
pip install lxml-4.6.3-cp38-cp38-win_amd64.whl

Для работы с картинками использую Pillow.

#### Не будет работать если ...  
Многие, крупные особенно, магазины защищаются от такого парсинга в лоб (блок по куке, блок по ip). 
С магазинами где фронт на js фреймворках (angular/react/vue) тоже не пройдет