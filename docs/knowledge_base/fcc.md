---
icon: simple/fcc
tags:
    - first_gen
    - second_gen
    - third_gen
title:  FCC хак
description: Как разблокировать полную мощность и увеличить кол-во каналов
---
# FCC hack

* :material-roman-numeral-1: первое поколение:
    - Air Unit + DJI FPV Goggles/DJI FPV Goggles V2
    - Caddx Vista + DJI FPV Goggles/DJI FPV Goggles V2
* :material-roman-numeral-2:/:material-roman-numeral-3: второе и третье поколение:
    - Air Unit + Goggles 2/Integra
    - Caddx Vista + Goggles 2/Integra
    - o3 Air Unit + DJI FPV Goggles V2/Goggles 2/Integra/Goggles 3
    - o4 Air Unit + Goggles 2/Integra/Goggles 3/Goggles N3
    - o4 Air Unit Pro + Goggles 2/Integra/Goggles 3/Goggles N3

=== ":material-roman-numeral-1: первое поколение"
    
    
    ???+ info
        * во время хака очков, должен быть выключен юнит
        * во время хака передатчика, должны быть выключены очки
        * если создаёте файлы самостоятельно, проверяйте корректность расширения:
        * :material-microsoft-windows: проводник → Вид → Параметры → Вид → деактивировать пункт _“Скрывать расширения для зарегистрированных типов файлов”_
        * :material-apple-finder: Finder → Настройки → Дополнения → активировать пункт Показывать все расширения имен файлов

    1. naco.txt + naco\_pwr.txt <a href="https://storage.yandexcloud.net/djifpv.ru/naco_files.zip" target="_blank">скачать файлы:material-file-download-outline:</a>
    2. извлечь из архива
        - oчки
            - если достаточно 700mW - можно ничего не делать;
            - если необходимо увеличение мощности:
                - скопировать файл naco\_pwr.txt на SD карту очков;
                - перезагрузить очки (выключить, включить, дождаться загрузки)
        - Air Unit/Caddx Vista
            - Скопировать файл _naco.txt_ на SD Air Unit’а или напрямую на Caddx Vista (да, в Vista нет SD карты, но она отлично определяется как съёмный диск);
            - перезагрузить передатчик (выключить, включить)

    !!! success ""
        _Оперативно определить успешность хака можно по кол-ву каналов в 25Мбит - каналов должно быть 8 (4 в 50Мбит, соответственно)._


    Хранить файлы на девайсах после процедуры необязательно.

    В случае, если после обновления прошивки очков и видеомодуля FCC режим не активен, повторить процедуры;

    Если запутались в файлах и сомневаетесь, копируйте оба, в очки и видеомодуль.

    ???+ info "список параметров naco.txt"
        * 1 – FCC mode for US, 8 Channels
        * 2 – FCC mode for Canada 4 Channels
        * 3 – HK CE 4 Channels
        * 4 – CN SRRC 4 Channels
        * 5 – JP Japan 3 Channels
        * 6 – KR Korea 4 Channels
        * 7 – BR Brazil 4 Channels
        * 8 – FR CCA 4 Channels

=== ":material-roman-numeral-2:/:material-roman-numeral-3: второе и третье поколение"
    
    ???+ info
        * DJI сильно упростили FCC hack во втором и следующем поколениях, теперь достаточно добавления одного файла в очки
        * в архиве пустой файл, без расширения, с нулевым весом - это нормально

    1. ham_cfg_support <a href="https://storage.yandexcloud.net/djifpv.ru/ham_cfg_support.zip" target="_blank">скачать файл:material-file-download-outline:</a>
    2. извлечь из архива
    3. поместить в корень microSD карты очков

    !!! success ""
        _Оперативно определить успешность хака можно по кол-ву каналов в 40Mhz - каналов должно быть 3._
