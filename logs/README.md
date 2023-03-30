Дано:

access логи nignx в формате:

```
log_format compression '$remote_addr - $remote_user [$time_local] '
                           '"$request" $status $body_bytes_sent '
                           '"$http_referer" "$http_user_agent"';
```

Задача1:

Получить 10 уникальных ip адресов с самым высоким `$body_byte_sent` (идет после статуса).

Решение должно быть в виде pipe:


```
cat access.log | awk '{if ($10 != "-") print $1,$10}'| sort -rnk2 | uniq -c  | head -10
```

Прислать команду в текстовом виде и приложить скриншот с результатом
![task2.1](https://github.com/mishalipatnikov/questions_touch_instinct/blob/main/result/task2.1.png)
Задача2:

Получить кол-во уникальных ip адресов у которых `$body_byte_sent` НЕ равно "-"

Прислать команду в текстовом виде и приложить скриншот с результатом

```
cat access.log | awk '{if ($10 != "-") print $1;}' | sort | uniq -c | sort -rn | wc -l
```
![task2.2](https://github.com/mishalipatnikov/questions_touch_instinct/blob/main/result/task2.2.png)
