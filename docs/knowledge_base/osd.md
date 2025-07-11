---
icon: material/symbol
title: Настройка OSD
description: 'Пошаговая инструкция для актуальных прошивок полетных контроллеров: Betaflight, INAV, Kiss Ultra'
glightbox: true
---

# Настройка OSD

!!! abstract "замечание"

    <p>на текущий момент здесь описаны настройки для актуальных версий полетных контроллеров + очков, которые могут нативно отображать полноценное HD OSD
    <p>легаси настройки + настройки девайсов с WTFOS будут добавлены чуть позже

## физическое подключение юнита

!!! danger
    __всегда__ внимательно проверяйте распиновку полетника, идеальный вариант - с мультиметром

    китайцы иногда забывают актуализировать документацию или шелкографию на полетнике, и юнит получает 6s на UART

??? warning
    в сети можно встретить информацию что для o3 Air Unit необходимы строго 6 проводов, иначе юнит не будет выходить из режима низкого энергопотребления - это не соответствует действительности

    DJI не меняли распиновку или логику работы подключения с момента релиза DJI Digital FPV System в 2019 году, если вы не летаете с аппаратурой DJI - S.Bus и вторая земля __не нужны__, а иногда даже вредны, т.к. по общепринятой практике приемники управления подключаются к UART 2, что приводит к следующей ситуации - в случае если внешний приемник (TBS/ELRS/etc) и DJI HD link (S.Bus) одновременно подключены к одному и тому же RX 2, полетный контроллер не сможет самостоятельно выделить «нужную» связь и даже при наличии бинда не будет принимать сигнал со сторонней аппаратуры управления

- подключите видеопередатчик к нужному UART согласно инструкции полетного контроллера:

=== "FPV Air Unit"
    <figure markdown="span">
    ![Image title](./images/og_au_wiring_light.png){ width="100%" .on-glb }
    <figcaption>FPV Air Unit wiring</figcaption>
    </figure>
=== "Caddx Vista"
    <figure markdown="span">
    ![Image title](./images/caddx_vista_wiring_light.png){ width="100%" .on-glb }
    <figcaption>Caddx Vista wiring</figcaption>
    </figure>
=== "o3 Air Unit"
    <figure markdown="span">
    ![Image title](./images/o3_wiring_light.png){ width="100%" .on-glb }
    <figcaption>o3 Air Unit wiring</figcaption>
    </figure>
=== "o4 Air Unit"
    <figure markdown="span">
    ![Image title](./images/o4lite_wiring_light.png){ width="100%" .on-glb }
    <figcaption>o4 Air Unit wiring</figcaption>
    </figure>
=== "o4 Pro Air Unit"
    <figure markdown="span">
    ![Image title](./images/o4pro_wiring_light.png){ width="100%" .on-glb }
    <figcaption>o4 Pro Air Unit wiring</figcaption>
    </figure>

## настройка очков
в меню очков нужно выбрать режим холста HD
=== "язык интерфейса: русский"
    - Настройки :material-arrow-right: Экран :material-arrow-right: Режим холста :material-arrow-right: HD
    <figure markdown="span">
    ![Image title](./images/goggles_hd_ru_dark.png){ width="100%" .on-glb }
    <figcaption>выбор опции HD в очках</figcaption>
    </figure>
=== "язык интерфейса: english"
    - Settings :material-arrow-right: Display :material-arrow-right: Canvas Mode :material-arrow-right: HD
    <figure markdown="span">
    ![Image title](./images/goggles_hd_en_dark.png){ width="100%" .on-glb }
    <figcaption>выбор опции HD в очках</figcaption>
    </figure>
а так же выбрать формат работы OSD:

* Betaflight (для работы с Betaflight и KISS Ultra)
* INAV
=== "язык интерфейса: русский"
    - Настройки :material-arrow-right: Экран :material-arrow-right: Полетный контроллер :material-arrow-right: Betaflight
    <figure markdown="span">
    ![Image title](./images/goggles_fc_ru_dark.png){ width="100%" .on-glb }
    <figcaption>выбор опции ПК в очках</figcaption>
    </figure>
=== "язык интерфейса: english"
    - Settings :material-arrow-right: Display :material-arrow-right: Flight controller :material-arrow-right: Betaflight
    <figure markdown="span">
    ![Image title](./images/goggles_fc_en_dark.png){ width="100%" .on-glb }
    <figcaption>выбор опции ПК в очках</figcaption>
    </figure>

## настройки в зависимости от софта полетного контроллера:

### Betaflight

1. #### Ports.MSP 
    во вкладке портов необходимо активировать MSP на том порту, куда подключены RX и TX видеопередатчика
    <figure markdown="span">
    ![Image title](./images/ports_light.webp#only-light){ width="100%" .on-glb }
    ![Image title](./images/ports_dark.webp#only-dark){ width="100%" .on-glb }
    <figcaption>Betaflight Ports MSP </figcaption>
    </figure>
2. #### Ports.Peripherials 
    начиная с версии Betaflight 4.4 небходимо выбрать в колонке периферия опцию VTX(MSP+Displayport)
    <figure markdown="span">
    ![Image title](./images/beta_msp_light.webp#only-light){ width="100%" .on-glb }
    ![Image title](./images/beta_msp_dark.webp#only-dark){ width="100%" .on-glb }
    <figcaption>выбор опции в периферии</figcaption>
    </figure>
    - [опционально] можно проверить в консоли, что опция MSP+Displayport включилась корректно
        - введите следующую команду в консоль Betaflight конфигуратора 
        ``` title='Betaflight CLI'
        get display
        ```
        - проверьте полученный ответ на команду:
        === "правильный ответ консоли"
            ``` hl_lines="5"
            # get display
            vbat_display_lpf_period = 30
            Allowed range: 1 - 255

            osd_displayport_device = MSP
            Allowed values: NONE, AUTO, MAX7456, MSP, FRSKYOSD

            displayport_msp_col_adjust = 0
            Allowed range: -6 - 0

            displayport_msp_row_adjust = 0
            Allowed range: -3 - 0

            displayport_msp_fonts = 0,1,2,3
            Array length: 4

            displayport_msp_use_device_blink = OFF
            Allowed values: OFF, ON
            ```
        === "неправильный ответ консоли"
            ``` hl_lines="5"
            # get display
            vbat_display_lpf_period = 30
            Allowed range: 1 - 255

            osd_displayport_device = AUTO
            Allowed values: NONE, AUTO, MAX7456, MSP, FRSKYOSD
            Default value: MSP

            displayport_msp_col_adjust = 0
            Allowed range: -6 - 0

            displayport_msp_row_adjust = 0
            Allowed range: -3 - 0

            displayport_msp_fonts = 0,1,2,3
            Array length: 4

            displayport_msp_use_device_blink = OFF
            Allowed values: OFF, ON
            ```
        - если вы видите __osd_displayport_device = AUTO__ исправить можно через консоль, введите следующую команду:
        ``` title='Betaflight CLI'
        set osd_displayport_device = MSP
        ```
        - не забывайте сохранить новые настройки:
        ``` title='Betaflight CLI'
        save
        ```
3. #### OSD.Video Format

    Betaflight конфигуратор :material-arrow-right: OSD :material-arrow-right: Video Format :material-arrow-right: установите опцию HD
    <figure markdown="span">
    ![Image title](./images/osd_light.webp#only-light){ width="100%" .on-glb }
    ![Image title](./images/osd_dark.webp#only-dark){ width="100%" .on-glb }
    <figcaption>HD OSD</figcaption>
    </figure>

### INAV

!!! warning "важно"
    проверяйте прошивку очков на соответствие версии

    | **очки**        | **версия прошивки** |
    |:----------------|--------------------:|
    | Goggles 2       | v01.12.0000 или выше|
    | Goggles integra | v01.08.0000 или выше|
    | Goggles 3       | v01.00.0800 или выше|
    | Goggles N3      | v01.00.0400 или выше|

1. #### Настройка очков 
    === "язык интерфейса: русский"
        - Настройки :material-arrow-right: Экран :material-arrow-right: Полетный контроллер :material-arrow-right: INAV
        <figure markdown="span">
        ![Image title](./images/goggles_inav_ru.png){ width="100%" .on-glb }
        <figcaption>выбор опции ПК в очках</figcaption>
        </figure>
    === "язык интерфейса: english"
        - Settings :material-arrow-right: Display :material-arrow-right: Flight controller :material-arrow-right: INAV
        <figure markdown="span">
        ![Image title](./images/goggles_inav_en.png){ width="100%" .on-glb }
        <figcaption>выбор опции ПК в очках</figcaption>
        </figure>

2. #### Ports.Peripherials 
    на нужном UART выбрать в колонке периферия опцию MSP DisplayPort
    <figure markdown="span">
    ![Image title](./images/inav_ports_full.png){ width="100%" .on-glb }
    <figcaption>INAV peripherials options list</figcaption>
    </figure>
    <figure markdown="span">
    ![Image title](./images/inav_ports_short.png){ width="100%" .on-glb }
    <figcaption>INAV ports and peripherials configuration</figcaption>
    </figure>

3. #### OSD.Video Format
    INAV конфигуратор :material-arrow-right: OSD :material-arrow-right: Video Format :material-arrow-right: установите опцию DJI_NATIVE
    <figure markdown="span">
    ![Image title](./images/inav_osd_short.png){ width="100%" .on-glb }
    <figcaption>INAV OSD DJI_NATIVE</figcaption>
    </figure>    
    <figure markdown="span">
    ![Image title](./images/inav_osd_full.png){ width="100%" .on-glb }
    <figcaption>INAV OSD options list</figcaption>
    </figure>

### KISS Ultra

!!! example "info"
    DJI не поддерживает нативные шрифты Ultra, на текущий момент актуальное поколение железа DJI из коробки в связке с Ultra работает с таблицей символов Betaflight версии 4.4 (включая HD шрифты)


1. #### Advanced.Serial Configuration
    - Во вкладке Advanced активируйте :material-checkbox-marked-outline: «Use advanced serial configuration» в блоке Serial Configuration
    - на нужном порту выберите из выпадающего списка MSP OSD (HD)
    <figure markdown="span">
    ![Image title](./images/ultra_serial.webp){ width="100%" .on-glb }
    <figcaption>Ultra Serial Configuration</figcaption>
    </figure>

2. #### Advanced.MSP OSD
    - Во вкладке Advanced выберите DJI o3 HD в блоке MSP OSD
    <figure markdown="span">
    ![Image title](./images/ultra_osd_type.webp){ width="100%" .on-glb }
    <figcaption>Ultra MSP OSD</figcaption>
    </figure>

3. #### OSD Mirror
    - сохраните необходимый набор элементов в OSD Mirror на вкладке OSD
    
    <figure markdown="span">
    ![Image title](./images/ultra_osd_format.webp){ width="100%" .on-glb }
    <figcaption>Ultra OSD Mirror</figcaption>
    </figure>