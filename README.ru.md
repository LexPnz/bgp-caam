# BGP Antifilter Prefixes
[English](README.md) | [Русский](README.ru.md)

Оптимизированные списки BGP-префиксов формируются на основе [antifilter.download](https://antifilter.download/) с дополнительными корректировками по доменам и ASN.

Списки предназначены для маршрутизации и фильтрации сетевого трафика с использованием BGP-совместимых маршрутизаторов и программного обеспечения.

## Файлы

| Файл | Описание |
|---|---|
| [`networks.txt`](networks.txt) | Список IPv4 CIDR-префиксов, один префикс на строку |
| [`mikrotik.rsc`](mikrotik.rsc) | Скрипт импорта адресов в MikroTik RouterOS |

## Дополнительные домены

В список добавлены:

- `rutracker.org`
- `nnmclub.to`
- `4pda.to`
- `nextdns.io`
- `stackoverflow.com`
- `mobileproxy.space`

## Дополнительные ASN

Добавлены сети следующих автономных систем Apple:

| ASN | Организация |
|---:|---|
| AS714 | APPLE |
| AS6185 | APPLE |

## Исключённые российские ASN

Из российского списка префиксов исключены:

| ASN | Организация |
|---:|---|
| AS201012 | Avito LLC |
| AS204720 | CDNetworks Global Cloud Network |
| AS210756 | EdgeCenter LLC |
| AS211609 | OKKO |
| AS29182 | RU-JSCIOT |
| AS41718 | VITRINA TV |
| AS47541 | VK SPB |
| AS48018 | FORNEX |
| AS51115 | HLL |
| AS57363 | CDNVIDEO |
| AS57724 | DDOS GUARD |

## Использование

### Скачать список префиксов

```bash
wget -O networks.txt \
  https://raw.githubusercontent.com/LexPnz/bgp-caam/main/networks.txt
  ```
  
  ### MikroTik RouterOS
  
  ```routeros
  /tool fetch url="https://raw.githubusercontent.com/LexPnz/bgp-caam/main/mikrotik.rsc" dst-path=mikrotik.rsc
  /import file-name=mikrotik.rsc
  ```
  
  ## Обновление списков
  
  Списки автоматически формируются на основе таблиц маршрутизации BIRD и публикуются в этом репозитории.
  
  Оба формата экспорта генерируются из одного набора префиксов.
  
  ## Отказ от ответственности
  
  Проект предоставляет списки BGP-префиксов на основе внешних источников и дополнительных правил фильтрации.
  
  Принадлежность IP-префиксов, BGP-анонсы и сетевые назначения могут меняться со временем. Проверяйте содержимое списков перед применением в производственной инфраструктуре.