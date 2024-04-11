<h1> Компьютерные сети: Лабораторная работа №1</h1>
<li>Сдающий: <b>Ващук Лев Александрович</b> 
<li>Группа: <b>з5130902/10202</b> 
<li>WireShark анализ движения пакетов в сети.</li>
<hr>
<h2>Обзор WireShark</h2>
Wireshark – это широко распространённый инструмент для захвата и анализа сетевого трафика, 
который активно используется как для образовательных целей, так и для устранения неполадок на компьютере или в сети. <br>
Wireshark работает практически со всеми протоколами модели OSI, обладает понятным для обычного пользователя интерфейсом и удобной системой фильтрации данных. 
Помимо всего этого, программа является кроссплатформенной и работает под самыми разными ОС.
<hr>
<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/6bba947ff829bc71132cfcd91eebd8b01f20c66e/1.png">
<p align=center>Рисунок 1 - Выбор сетевого интерфейса</p>
При запуске WireShark нам дается возможность выбора сетевого интерфейса, через который мы сможем отслеживать движущийся трафик.
Я выбираю беспроводной интрефейс wlan0.<br><br>


<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/6bba947ff829bc71132cfcd91eebd8b01f20c66e/2.png">
<p align=center>Рисунок 2 - Главное рабочее пространство</p>
Мы представлены перед главным рабочим пространством WireShark. Оно делится на 3 зоны:<br>
1) Весь трафик, который способен увидеть выбранный сетевой интерфейс. В моем случае wlan0;<br>
2) Расшифрованный выбраный пакет. Тут мы можем увидеть информацию о заголовках разного уровня;<br>
3) Тут мы видим заголовок в зашифрованном виде. <br><br>

<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/6bba947ff829bc71132cfcd91eebd8b01f20c66e/3.png">
<p align=center>Рисунок 3 - Расшифровка заголовков</p>
На рисунке 3 мы наблюдаем то, как можно расшифровать информацию, передаваемую в пакетах. На этом примере мы видим адрес отправителя в заголовке IP и
то, как эта информация выглядт в зашифрованом варианте.<br><br>

<h2>Захват и анализ интересующих нас пакетов</h2>
Приведу пример перехвата пакетов локально между Servlet контейнером и софтом для тестирования API - Postman.
Отправим запрос на локальный веб сервер, как продемонстрировано на рисунке 4:<br>
<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/49e1462c24278557b2b4e895ad71eff5fa0f4ec1/4.png">
<p align=center>Рисунок 4 - Отправка запроса локальному серверу</p><br>

В WireShark настроим фильтр для удобства работы:

```
port 8080
```
Получаем список пакетов и видим наш запрос на рисунке 5:
<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/e8363d58f2fca7d2dbe3d17bc0e233c8f6af84b7/5.png">
<p align=center>Рисунок 5 - Наш запрос</p><br>

На рисунке 6 в свою очередь можно увидеть ответ сервера:
<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/1ae8aa8e0781aedefd7601d3c4161b98437400d3/7.png">
<p align=center>Рисунок 6 - Наш ответ</p><br>

На рисунке 7 мы видим, как этот ответ продублирован в Postman:
<img src="https://github.com/narcissusTheFlower/networking-lab1/blob/1ae8aa8e0781aedefd7601d3c4161b98437400d3/6.png">
<p align=center>Рисунок 7 - Ответ в Postman</p><br>

