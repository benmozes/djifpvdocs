---
icon: material/bug-outline
title: Известные баги
description: Известные на текущий момент баги и особенности
glightbox: true
---

# Известные баги

* :material-bug-play-outline:{ .red_cross } баг не исправлен
* :material-bug-check:{ .green_check } баг исправлен

## :material-bug-check:{ .green_check }  Goggles 3 и Goggles N3 мешают ELRS 2.4

!!! note ""
    начиная с Goggles 3 и Goggles N3 DJI перевели протокол управления юнитами из связки 
    !!! quote ""
        FPV Remote Controller :material-arrow-left-right: Air Unit</br>
        FPV Remote Controller :material-arrow-left-right: Goggles
    в связку 
    !!! quote ""
        FPV Remote Controller :material-arrow-left-right: Goggles :material-arrow-left-right: Air Unit
    
    это позволило убрать кучу железа из Remote Controller и оставить только чипы связи для <a href="https://fpvwiki.co.uk/dji-fpv-remote-v3" target="_blank">2.4 GFSK</a>, поэтому, в случае отсутствия FRV Remote Controller, очки добавляют шум в 2.4 радиоэфир 

    ELRS 2.4 до версии 3.5.3 включительно мог <a href="https://github.com/ExpressLRS/ExpressLRS/pull/3154" target="_blank">принять этот шум за свой сигнал</a>, что приводило к драматическому снижению LQ или даже RXLoss

!!! success "fixed"
    исправлено в <a href="https://github.com/ExpressLRS/ExpressLRS/releases/tag/3.5.4" target="_blank">ExpressLRS V3.5.4</a>

## :material-bug-check:{ .green_check }  низкий битрейт o4/o4 pro

в авто режиме каналов o4 юниты выдают не больше 15/30Mbps

!!! success "fixed"
    прошейте o4 Air Unit/o4 Air Unit Pro на версию v01.00.0300 или выше