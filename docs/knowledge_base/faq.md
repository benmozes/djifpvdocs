---
icon: material/frequently-asked-questions
title: FAQ
description: часто задаваемые вопросы
glightbox: true
---

## какие лимиты дальности?
!!! tip ""
    | Air Unit                     |             FPV Goggles |       FPV Goggles V2 |       Goggles 2/Integra |       Goggles 3 |       Goggles N3 |
    |:-----------------------------|------------------------:|----------------------:|-------------------------:|-----------------:|------------------:|
    |     FPV Air Unit/Caddx Vista |                 13.4км |               13.4км |                    30км |              ❌ |               ❌ |
    |     o3 Air Unit              |                    ❌ |               23.4км |                  23.4км |           <span style="background-color: #ffeeba; padding: 0.2em 0.4em; border-radius: 4px; color: #212529;">25.5км</span>[^1] |               ❌ |
    |     o4 Air Unit              |                    ❌ |                  ❌ |                  25.5км |           25.5км |            25.5км |
    |     o4 Air Unit Pro          |                    ❌ |                  ❌ |                  25.5км |           28.3км |            28.3км |

[^1]: по Goggles 3 + o3 Air Unit информация не подтверждена

## что с чем совместимо?
!!! tip ""
    см. [общая таблица совместимости](compatibility.md#общая-таблица-совместимости)

## какой ассистент нужен?
!!! tip ""
    см. [DJI Assistant 2](dji_assistant.md)

    !!! note "если у тебя первое поколение железа:"

        * DJI Air Unit
        * Caddx Vista
        * DJI FPV Goggles
        * DJI FPV Goggles V2

        скачивай [DJI Assistant 2 (DJI FPV series)](dji_assistant.md#dji-assistant-2-dji-fpv-series)

    !!! note "если у тебя второе и выше поколение железа:"

        * DJI o3 Air Unit
        * DJI o4 Air Unit
        * DJI o4 Air Unit Pro
        * DJI Goggles 2
        * DJI Goggles Integra
        * DJI Goggles 3
        * DJI Goggles N3

        скачивай [DJI Assistant 2 (Consumer Drone Series)](dji_assistant.md#dji-assistant-2-consumer-drone-series)

## можно ли заменить антенны на очках?
!!! tip ""
    | очки                   | возможность замены антенн   | разъём   |
    |:-----------------------|------------------------------:|--------------:|
    | DJI FPV Goggles        | да, все четыре                | RP-SMA        |
    | DJI FPV Goggles V2     | да, все четыре                | RP-SMA        |
    | DJI Goggles 2          | да, две внешние               | MCX           |
    | DJI Goggles Integra    | ❌                            | ❌            |
    | DJI Goggles 3          | ❌                            | ❌            |
    | DJI Goggles N3         | ❌                            | ❌            |

## как сделать хак?
!!! tip ""
    см. [FCC hack](fcc.md#fcc-hack)

## как настроить OSD?
!!! tip ""
    см. [Настройка OSD](osd.md#настройка-osd)

## можно ли заменить coaxial шлейфы o4 и o4 pro?
!!! success "можно"
    они одинаковые по распиновке

## можно ли записывать OSD на видео?
!!! failure "нельзя - на старом поколении очков:"

    * FPV Goggles (V1)
    * FPV Goggles V2

!!! success "можно - на новом поколении очков:"

    * Goggles 2
    * Goggles Integra
    * Goggles 3
    * Goggles N3
    
    === "RU"
        настройки → камера → расширенные настройки камеры → запись обзора камеры :material-toggle-switch-outline:
    === "EN"
        settings → camera → advanced camera settings → camera view record :material-toggle-switch-outline:

## какие настройки нужны для стабилизации видео в Gyroflow?
!!! tip ""
    * отключить внутреннюю стабилизацию RockSteady (EIS)
    * установить угол камеры широкий/wide