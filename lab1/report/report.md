---
# Front matter
lang: ru-RU
title: "Лабораторная работа №1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
author: "Валиева Найля Разимовна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Задание

1. Проверить настройки VirtualBox. Создать новую вирутальную машину Base.
2. Запустить виртуальную машину Base. Провести ее конфигурацию.
3. Подключиться к вирутальной машине, используя созданную учетную записью.
4. Создать на основе виртуальной машины Base машину Host2.

# Выполнение лабораторной работы

1. Запустила виртуальную машину и проверила в свойствах VirtualBox месторасположение каталога для виртуальных машин (рис -@fig:001).

![Окно «Настройки» VirtualBox](image/1.png){ #fig:001 width=70% }

Создала виртуальную машину, указала ее имя - Base, указала тип операционной системы - Linux, RedHat(32 bit) (рис -@fig:002)

![Окно «Имя машины и тип ОС»](image/2.png){ #fig:002 width=70% }

Указала размер основной памяти виртуальной машины - 1024 МБ (рис -@fig:003)

![Окно «Размер основной памяти»](image/3.png){ #fig:003 width=70% }

Задала конфигурацию жёсткого диска — загрузочный (рис -@fig:004), VDI (BirtualBox Disk Image) (рис -@fig:005), динамический виртуальный диск (рис -@fig:006).

![Окно «Виртуальный жесткий диск»](image/4.png){ #fig:004 width=70% }

![Окно «Мастер создания нового виртуального диска»](image/5.png){ #fig:005 width=70% }

![Окно «Дополнительные атрибуты виртуального диска»](image/6.png){ #fig:006 width=70% }

Задала размер диска — 40 ГБ (рис -@fig:007)

![Окно «Расположение и размер виртуального диска»](image/7.png){ #fig:007 width=70% }

Выделила в окне менеджера VirtualBox виртуальную машину \textit{Base}, и открыла окно \textit{Настройки}. Проверила, что папка для снимков виртуальной машины Base имеет верный путь (рис -@fig:008)

![Окно «Настройки» виртуальной машины Base](image/8.png){ #fig:008 width=70% }

Добавила новый привод оптических дисков и выбрала образ \textit{CentOS-6.6-i386-bin-DVD1.iso} (рис -@fig:009, рис -@fig:010)

![Окно «Носители» виртуальной машины Base: выбор образа оптического диска](image/9.png){ #fig:009 width=70% }

![Окно «Носители» виртуальной машины Base](image/10.png){ #fig:010 width=70% }

2. Запустила виртуальную машину Base, выбрала установку системы на жесткий диск (рис -@fig:011)

![Запуск установки системы](image/11.png){ #fig:011 width=70% }

Установила русский язык для интерфейса (рис -@fig:013) и раскладки клавиатуры (рис -@fig:014)

![Виртуальная машина Base. Установка русского языка](image/12.png){ #fig:012 width=70% }

![Виртуальная машина Base. Установка русского языка для раскадки клавиатуры](image/13.png){ #fig:013 width=70% }

Указала \textit{Стандартные накопители} (рис -@fig:014) для установки ОС. В окне конфигурации жёсткого диска выбрала \textit{«Да, удалить данные»}  

![Виртуальная машина Base](image/14.png){ #fig:014 width=70% }

В качестве имени машины указала \textit{«nrvalieva.localdomain»} (рис -@fig:017). Указала часовой пояс «Москва», установила пароль для root.

![Задание сетевого имени виртуальной машины](image/15.png){ #fig:015 width=70% }

При конфигурировании размера жёсткого диска указала \textit{«Всё пространство»} (рис -@fig:016).

![Конфигурация размера жесткого диска](image/16.png){ #fig:016 width=70% }

Выбрала вариант стандартной установки CentOS.

Завершила установку операционной системы и перезагрузила её.

Запустила виртуальную машину Base и настроила её (рис -@fig:017).

![Настройка виртуальной машины: дата и время](image/17.png){ #fig:017 width=70% }

3. Подключилась к виртуальной машине с помощью созданной учётной записи (рис -@fig:018)

![Подключение к виртуальной машине](image/18.png){ #fig:018 width=70% }

На виртуальной машине Base запустила терминал, перешла под учетную запись \textit{root} с помощью команды \textit{su} (рис -@fig:019).

![Подключение к виртуальной машине](image/19.png){ #fig:019 width=70% }

С помощью команды \textit{yum update} обновила системные файлы и установила \textit{mc} (рис -@fig:020).

![«yum update» и «yum install mc»](image/20.png){ #fig:020 width=70% }

4. Произвела действия для того, чтобы другие виртуальные машины могли использовать машину Base и её конфигурацию как базовую (рис -@fig:030, рис -@fig:031).

![Менеджер виртуальных носителей: освобождение жесткого диска](image/21.png){ #fig:021 width=70% }

![Менеджер виртуальных носителей: множественное подключение](image/22.png){ #fig:022 width=70% }

На основе виртуальной машины Base создала машину Host2, выбрав при конфигурации виртуального жесткого диска «Использовать существующий жесткий диск»
Base.vdi (рис -@fig:023, рис -@fig:023).

![Выбор «Использовать существующий жесткий диск» при создании машины Host2](image/23.png){ #fig:023 width=70% }

![Созданная виртуальная машина Host2](image/24.png){ #fig:024 width=70% }

# Выводы

Приобрела практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.
