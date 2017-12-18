# Возможности

![](https://i.imgur.com/6bFXKxU.jpg)

| Параметр      | Значение      |
| ------------- |:-------------:|
| Рабочая область обработки (ДхШхВ), мм  | 400x450x120   |
| Мощность шпинделя, кВт | 2.2    |
| Дискретность позиционирования, мм | 0.0016 |
| Точность позиционирования, мм/100 мм | 0.05 |
| Тип цанги | ER |
| Прошивка по умолчанию | [Repetier FW](https://www.repetier.com/documentation/repetier-firmware/), CNC mode M453 |
| Baudrate по умолчанию | 250 000 |

## Удалённое управление

По умолчанию фрезер понимает [G-коды только формата Repetier](https://github.com/repetier/Repetier-Firmware/wiki/G-codes). Соответственно фрезер может управляться через [Octoprint](http://octoprint.org/) или [Repetier-Server](https://www.repetier-server.com/)

Также на фрезер можно залить прошивку Grbl. Подробней о её преимуществах [тут](https://github.com/FabLab61/quick_start/wiki/Shapeoko-2#%D0%92%D0%B5%D1%80%D1%81%D0%B8%D1%8F-09)


## Основные G-коды

```
М3 - включить шпиндель
М5 - выключить шпиндель
M4 - смена направления вращения
G28 - home all axes
G92 X0 y0 z0 - обнуление координат (после подведения фрезы в точку отсчета на материале)
```


## Пострпроцессоры

Производитель рекомендует использовать ArtCAM. У него конечно есть [бесплатная версия под Windows](http://www.artcam.com/free/), но софт проприетарный поэтому его рассматривать не будем.


## [gcodetools](https://github.com/cnc-club/gcodetools)

Отличный плагин для Inkscape. Мануал [здесь](http://www.cnc-club.ru/gcodetoolsru), есть [обучающие видео на русском](http://www.cnc-club.ru/forum/viewtopic.php?f=15&t=34&start=400&p=27427#p27427).

Установка на Linux:

```
cd /usr/share/inkscape/extensions
sudo wget https://github.com/cnc-club/gcodetools/archive/master.zip
unzip master.zip
rm master.zip
```

Примерная последовательность действий в gcodetools:

1) Orientation points (глубину указываем отрицательную)
2) Tools library
3) Path to Gcode


## Симуляция

Прежде чем загружать G-код в станок, его можно проверить. 

Наилучший софт для этого - [Camotics](http://camotics.org/) (бывший `openscam`)

Если на Ubuntu после запуска Camotics говорит: 

```
openscam: error while loading shared libraries: libv8.so.3.14.5: cannot open shared object file: No such file or directory
```

Нужно установить `libv8-dev` : `sudo apt-get install libv8-dev`