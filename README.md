# Домашнее задание к занятию 2 «Кластеризация и балансировка нагрузки» Бережок А.

## Задание 1
### Запустите два simple python сервера на своей виртуальной машине на разных портах
### Установите и настройте HAProxy, воспользуйтесь материалами к лекции по ссылке
### Настройте балансировку Round-robin на 4 уровне.
### На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy.
## Решение
### В терминале запустили в 2 сервера python3 на разных портах.
### Настроили HAProxy для балансировки на уровне L4
### ![](https://github.com/Berezhok/hw_haproxy_nginx/blob/main/img/HAProxy_conf.png)
### ![](https://github.com/Berezhok/hw_haproxy_nginx/blob/main/img/curl_servers.png)
### 
### 
## Задание 2
### Запустите три simple python сервера на своей виртуальной машине на разных портах
### Настройте балансировку Weighted Round Robin на 7 уровне, чтобы первый сервер имел вес 2, второй - 3, а третий - 4
### HAproxy должен балансировать только тот http-трафик, который адресован домену example.local
### На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него.
## Решение
### Конфигурационный файл HAProxy
### ![](https://github.com/Berezhok/hw_haproxy_nginx/blob/main/img/ACL_local.png)
### Видно балансировку серверов по весу, сервер 3 появляется намного чаще сервера 2 и 1
### ![](https://github.com/Berezhok/hw_haproxy_nginx/blob/main/img/L7_s3_weight.png)
### Идет переход только при использовании example.local
### ![](https://github.com/Berezhok/hw_haproxy_nginx/blob/main/img/fail_ACL_no_local.png)
### Балансировка по L4 идет без веса. На все сервера идет запрос одинаково.
### ![](https://github.com/Berezhok/hw_haproxy_nginx/blob/main/img/L4_weight.png)

