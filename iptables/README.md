Задача1:

Написать команду определения ip адреса для домена `ya.ru` используя dns сервер `8.8.8.8`.

Прислать команду в текстовом виде и приложить скриншот с результатом

```
dig ya.ru
```
![task1.1](https://github.com/mishalipatnikov/questions_touch_instinct/blob/main/result/task1.1.png)
Задача2:

С помощью `tcpdump` сделать дамп udp-пакетов, которые отправляются на `8.8.8.8`.

Прислать команду и результат дампа в виде файла. В файле должен быть 1 пакет.

````
sudo tcpdump -i any -nn host 8.8.8.8 and udp -w dump.pcap
````

Задача3:

Дропать пакеты полученные от `8.8.8.8` используя команду `iptables`.

Прислать команду и скриншот неудачной попытки выполнения команды из задачи1.

```
sudo iptables -A INPUT -s 8.8.8.8 -j DROP
```
![task1.3](https://github.com/mishalipatnikov/questions_touch_instinct/blob/main/result/task1.3.png)
