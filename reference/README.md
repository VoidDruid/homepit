# Первоисточники моделей и размеров

Проверены 2026-11-04. Рабочие модели и правила их использования: [models/README.md](../models/README.md).

## Соберизавод 224, обычный профиль 20×40

- [Актуальный STEP](soberizavod/224-20x40-current.STEP) — исходник рабочей модели. [Скачать у изготовителя](https://www.soberizavod.ru/upload/iblock/635/lx36iwselpqgnpa66uwp4ndumteyxc9k/224-Konstruktsionnyy-profil-20kh40.STEP).
- [Размерный чертёж](soberizavod/224-20x40.pdf). [PDF изготовителя](https://www.soberizavod.ru/upload/iblock/fc4/h309af7dvi0z2a7k7bs60ieed0qycctt/224-Konstruktsionnyy-profil-20kh40.pdf).
- [Сохранённая карточка товара](soberizavod/224-product.html). [Карточка на сайте](https://www.soberizavod.ru/catalog/seriya_20_obychnyy_paz_anodirovannyj/profil_konstruktsionnyy_20kh40_an_serebro_/).

Основные параметры: 40×20 мм, паз 6, шаг центральных каналов 20 мм, центральные каналы под M6, угловые под M4, наружный R1,5. По карточке: 2,51 см², 0,68 кг/м, Ix=1,06 см⁴, Iy=3,97 см⁴. Оси моментов инерции при расчёте согласовать с ориентацией сечения.

**В общем архиве 3D-моделей поставщика находится другая версия 224** с сечением 318,8155 мм². Рабочая модель построена по индивидуальному STEP выше, с сечением 251,2838 мм². Для дальнейшего выбора фурнитуры: [каталог и документация поставщика](https://www.soberizavod.ru/docs/).

## Thrustmaster T.Flight HOTAS NEO

- [Официальная монтажная схема](thrustmaster/T.FlightHotas4_Cockpit_setup.pdf). [PDF изготовителя](https://ts.thrustmaster.com/download/accessories/Manuals/TFH4/T.FlightHotas4_Cockpit_setup.pdf). Одна страница A3, масштаб 1:1, общие допуски ±0,1 мм; в штампе HOTAS 4, 25.02.2019.
- [Сохранённая страница поддержки NEO](thrustmaster/NEO-support.html) подтверждает прямую ссылку на эту схему. [Страница на сайте](https://support.thrustmaster.com/en/product/t-flight-hotas-neo-p-en/).
- [Руководство NEO PS](thrustmaster/T-Flight_Hotas_NEO_PS_user_manual.pdf). [PDF изготовителя](https://ts.thrustmaster.com/download/accessories/Manuals/TFHNEO/T-Flight_Hotas_NEO_PS_user_manual.pdf). Многоязычное; раздел EN в начале. Описывает разделение половин, кабельный канал, USB-C и RJ12.
- [Сохранённые характеристики продукции](thrustmaster/products.html). [Сайт изготовителя](https://www.thrustmaster.com/en-us/products/). Для NEO указан общий габарит 350×200×230 мм и масса 1425 г.
- [Монтажные данные JSON](thrustmaster/mounting_dimensions.json) — координаты M6, система координат, точки приближённой обводки и неизвестные параметры. Это производные данные проекта, не оригинальный чертёж.

Проверенной полной CAD-модели NEO не найдено. Официальная схема даёт центры четырёх M6, но не глубину резьбы, высоты отдельных оснований, ход рукояток или кабельные зазоры. Геометрия HOTAS X/4/One не считается автоматически идентичной NEO.

## Novation Launchpad S

- [Getting Started Guide EN](novation/Launchpad_S_Getting_Started_EN.pdf). [Официальная страница загрузок](https://downloads.novationmusic.com/novation/launchpad-mk1/launchpad-s). В руководстве нет механических размеров.
- [Сохранённая карточка Recordcase](novation/Launchpad-S-recordcase.html). [Карточка на сайте](https://www.recordcase.de/en/novation-launchpad-s). Указаны 240×240×20 мм и 0,717 кг. Это вторичный источник предварительного габарита; размеры проверить на имеющемся экземпляре.

Проверенной механической модели Launchpad S не найдено. Модели MK2, Mini, X и Pro не заменяют S. Для подложки нужны фактические размеры корпуса, ножек, углов, USB и подключённого штекера.

Исходные STEP/PDF/HTML сохранены без изменения содержимого; права остаются у их авторов.
