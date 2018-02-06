![](https://i.imgur.com/SZfF1O6.jpg)

# Возможности

Машинная вышивка на

* Форменная и спец одежда
* Шевроны (школьные и военные)
* Халаты 
* Полотенца 
* Постельное
* Футболки
* Подушки 
* Мягкие игрушки 
* Женские платья 
* Бейсболки и козырьки
* Корпоративный текстиль
* Детский текстиль

# Ключевые характеристики

- Размер рабочего поля (пяльцы) - 10x10 см. Максимум - 10 x 17 см (при наличии больших пялец)

[Оригинальное руководство]

# Пошаговая инструкция по вышивке логотипа из векторного файла
Швейная машина Brother Innov 950 принимает на вышивку два вида формата: pes и dst.

[Подробнее] о совместимости форматов и швейных машин.

### В данном гайде мы будем конвертировать в dst.
--------------------------------------------------------------------------------

1. Установите Inkscape
      ```bash
      sudo apt install inkscape
      ```
2. Расширение-конвертер Inkscape **SVG -> CSV** [источник][inkscape-embroidery]
   1. Установка зависимостей:
      #### Под Debian
      ```bash
      sudo apt install python-shapely python-appdirs python-networkx python-backports.functools-lru-cache
      ```
      #### Под Ubuntu
      ```bash
      # установка через apt
      sudo apt install python-shapely python-appdirs python-networkx
      # установка пакетного менеджера [pip]
      sudo apt install python-pip
      # установка через pip
      pip install --user backports.functools-lru-cache
      ```
      
   2. Установка расширения
      ```bash
      # клонирование репозитория в текущую папку
      git clone https://github.com/lexelby/inkstitch.git
      # перемещение содержимого в пользовотельскую папку Inkscape расширений
      mv inkscape-embroidery/* $HOME/.config/inkscape/extensions
      # удаление пустой папки
      rm -rf inkscape-embroidery
      ```
   3. Перезапустите Inkscape. Убедитесь, что расширение установлено: проверьте наличие пункта меню  **Расширения -> Embroidery** / Extensions -> Embroidery
   4. Пример использования:
      1. Изобразите прямоугольник 50*50мм с заливкой и обводкой (заливку желательно сделать полупрозрачной, передвинув ползунок альфа-канала влево или выкрутить совсем до нуля)
      2. Конвертируйте его в контур **Контур -> Оконтурить объект** / Path -> Object to Path
      3. Перейдите в меню **Расширения -> Embroidery -> Embroider...** / Extensions -> Embroidery -> Embroider...
      4. В меню **Output file format** выберите **Embroidermodder 2 CSV**
      5. Укажите директорию для сохранения (e.g.  /home/user/Documents)
      6. Отметьте **Live preview** для предпросмотра
      7. Примените **Aply** с дефолтными настройками

    Расширение создаст поверх вашего объекта чертеж, где обводка теперь зиг-заг, а заполнение - стежки. Файл *.csv (где * - имя вашего исходного SVG файла) будет сохранен в указанной вами директории.

	Если файл с таким именем, в этой директории, уже существует, то он будет переименован в *.csv.1 затем в *.csv.2 и так до *.csv.5 - 5 резерных копий. То есть ваш последний CSV будет сохранен в *.csv.	
	Для получения более качественного результата воспользуйтесь [гайдом][guide] по настройке параметров расширения.

4. Конвертер **CSV -> DST** [Embroidermodder]
   1. Клонируйте репозиторий Embroidermodder
      ```bash
      git clone https://github.com/Embroidermodder/Embroidermodder.git
      ```
   2. Соберите только конвертер libembroidery-convert
      ```bash
      cd Embroidermodder/libembroidery-convert/
	  #для сборки устанавливаем [qt-sdk] 
	  sudo apt install qt-sdk
	  #
      qmake && make
      # подробнее о возможны форматах конвертации
      ./libembroidery-convert --help
      ```
   3. Конвертируйте в DST-формат
      ```bash
      libembroidery-convert$ ./libembroidery-convert $HOME/Downloads/TEST/yourfile.csv $HOME/Downloads/TEST/yourfile.dst
      ```
   4. Переместите ваш *.dst файл в корень USB флешки и загрузите его в швейную машинку.
		## Готово! 
<img src="https://raw.githubusercontent.com/wiki/FablabTC/machines/images/sonic.png" width="250">

[Оригинальное руководство]: http://download.brother.com/welcome/doch000668/nv950ug01ru.pdf
[Подробнее]: https://www.embroidery.com/help.ec?docid=225
[inkscape-embroidery]: https://github.com/lexelby/inkscape-embroidery
[Embroidermodder]: https://github.com/Embroidermodder/Embroidermodder
[guide]: https://github.com/lexelby/inkscape-embroidery#embroidery-parameters
[python-backports.functools-lru-cache]: https://pypi.python.org/pypi/
[pip]: (https://en.wikipedia.org/wiki/Pip_(package_manager))
[qt-sdk]: (https://wiki.qt.io/Qt_SDK)

# Где покупать расходники?

- ## Ткань

- ## Нитки

- ## Иголки

- ## Стабилизирующий материал (флизелин)

### :pushpin: Напоминания:
- Чем меньше номер нити, тем толще нить, а чем выше номер иглы, тем толще игла.
