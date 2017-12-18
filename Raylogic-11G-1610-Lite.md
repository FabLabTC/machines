![](https://i.imgur.com/FjHedoQ.jpg)


# Возможности

| Параметр      | Значение      |
| ------------- |:-------------:|
| Размер поля гравировки/резки (мм) | 	1600Х1000   |
| Максимальная скорость гравировки (мм/сек) | 1000
| Точность гравировки (мм) 	| 0,01 |
| Тип лазерного излучения  | СО2  |
| Мощность лазерного излучателя | 	120 Вт   |
| Плата управления | 	RDLC633XG/634XG  |

Поддерживаемые форматы (RDWorks):

* AI (*.ai)
* DXF
* PLT 
* DST
* DSB
* WENTAI EPS (*.eps)
* CREACOMPO DAT FILES (*.dat)
* NC
* BMP
* RD Image (*.rdb)
* GIF
* JPEG
* PNG
* MNG
* ICON files (*.ico)
* CURSOR files (*.cur)
* TIFF files (*.tiff)
* TGA
* PCX
* WBMP
* WMF
* EMF
* JBG
* JP2 (*.j2c, *.jpc)
* PGX
* RAS
* PNM (*.pnm, *.pgm, *.ppm)
* SKA
* RAW

# Как вырезать чертёж, поэтапно

1. Установить [драйвера](http://reklab.ru/up/files2/USB-11G-drivers.rar)
2. Установить [RDWorks](https://yadi.sk/d/aK5SfS4N3P2NmU)
3. Отправляем чертеж в лазер с компьютера по LAN (кнопка Download в RDWorks), либо сохраняем на флешку и работаем с неё (с помощью функции SaveToUFile в RDWorks) 

Формат SVG к сожалению не поддерживается RDWorks, поэтому если исходный чертёж нарисован в SVG лучше всего его сохранить в DXF с помощью [Inkscape](https://inkscape.org/)

# Требования к макету

Для гравировки скорее всего потребуется оконтурить объект в Inkscape. В любом случае рекомендуется проверить макет в Simulation

# Возможные ошибки

## Not enough Exend Space

Гравировка расположена слишком близко к границе рабочей зоны, нужно чуть отодвинуть ноль

# Оптимальные параметры

| Материал  | Процесс   | Мощность, % | Скорость, мм/сек |
|:-------------|:-------------:|:------------:|:------------|
| Фанера ФК 4 мм | Резка | 80 | 20 |
| Фанера ФК 4 мм | Гравировка лайт | 30 | 500 |
| Фанера ФК 4 мм | Гравировка жирная | 40 | 500 |
| Габардин (ткань) | Резка | 40 | 9999 |
| Самоклеящийся фетр 4 мм, STANDERS CD60168-RU | Резка | 40 | 9999 |

Библиотеки параметров резки различных материалов от других фаблабов

https://github.com/FabLabLimerick/fablablimerick.github.io/wiki/Lasersaur-Material-Library

# Оценка стоимость

Стоимость резки зависит от суммарной длины прохода.
Стоимость материала зависит от суммарной площади.
Оба этих параметра можно посчитать по dxf файлу на сервисе от  [dangerousprototypes](http://dangerousprototypes.com/store/lasercut). Его исходный код [здесь](https://github.com/Esauromano/DirtyLaserQuotes) 

Для написания собственного софта можно использовать код от [LaserWeb](https://github.com/LaserWeb/LaserWeb4),[LasaurApp](https://github.com/stefanix/LasaurApp) и другие репозитории: https://github.com/nerdbeere/laser-calculator.

Есть даже целое [исследование](https://www.researchgate.net/publication/309258347_Calculation_of_laser_cutting_costs)

# Компоненты

Из чего собран лазер: