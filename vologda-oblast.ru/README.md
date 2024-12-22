# Архив сайта правительства Вологодской области

Архив сайта вместе с файлами `log` и `cdx` со всеми ссылками, а также база данных в формате `db` находятся в облачном хранилище Яндекс Диск по [ссылке](https://disk.yandex.ru/client/disk/Цифровой%20архив/vologda-oblast.ru).

## Результаты
![](https://github.com/rommap/archives_Vologda/blob/main/vologda-oblast.ru/Replay_Oblast.png)

Воспроизведение архива через сервис `ReplayWeb.page` демонстрирует с визуальной точки зрения лучший результат, что, вероятно связано с относительно малым использованием встроенного `javascript` на главной странице сайта. Большинство ссылок открываются корректно, за исключением тех, что ведут на внешние ресурсы, как например, ссылка на сайт Вологодской епархии.

## Извлечение метаданных
Метаданные анализировались с помощью следующих команд из библиотеки metawarc:
+ `analyze` - возвращает статистику с абсолютным и относительным числом и весом файлов каждого из типов, представленных в архиве
+ `metadata` - извлекает метаданные каждого файла архива в отдельный файл `digital_meta.jsonl`
+ `export` - извлекает заголовки HTTP, заголовки WARC или текстовое содержимое из архива в файл `headers.jsonl`

## Описание метаданных
`metawarc analyze vologda-oblast.ru.warc.gz`

```
mimes                                                                        files        size          share
-------------------------------------------------------------------------  -------  ----------  ------------- 
text/html                                                                    42364  4491309139   49.1056      
application/pdf                                                               1288  2369769225   25.9098      
image/jpeg                                                                   12957  1330834756   14.5506      
application/zip                                                                 92   388212498    4.24451     
application/msword                                                            1167   210591901    2.3025      
application/vnd.openxmlformats-officedocument.wordprocessingml.document       1365   107003983    1.16992     
application/vnd.ms-excel                                                       266    66967757    0.73219     
application/x-rar-compressed                                                     4    56263667    0.615157    
application/rtf                                                                 39    40347022    0.441133    
image/png                                                                      886    37007629    0.404622    
image/svg+xml                                                                   53    11269570    0.123215    
image/gif                                                                      150     9627906    0.105266    
application/vnd.openxmlformats-officedocument.presentationml.presentation        3     7394725    0.08085     
application/javascript                                                         197     6704746    0.0733061   
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet              163     6195033    0.0677332   
application/vnd.ms-powerpoint                                                    2     3571012    0.0390435   
text/css                                                                       254     2319839    0.0253639   
application/force-download                                                       5      478850    0.00523549  
font/woff                                                                        5      280769    0.00306978  
image/x-icon                                                                     3       33025    0.000361078 
application/xml                                                                  3       21578    0.000235922 
application/x-7z-compressed                                                      2       11621    0.000127058 
application/rss+xml                                                              1        6754    7.38446e-05 
application/vnd.ms-fontobject                                                    1        2717    2.97062e-05 
text/plain                                                                       1        2505    2.73883e-05 
application/json                                                                 1        1005    1.09881e-05 
application/x-javascript                                                         1         853    9.32625e-06 
#total                                                                       61273  9146230085  100

```

В отличие от архивов двух других сайтов, в этом наибольшее место занимает разметка `html`.

Так же как и на сайте Вологды и в отличие от Череповецкого, здесь архивированные файлы `zip` сильно уступают отдельным `pdf`, которые к слову, в среднем весят значительно меньше, чем на ресурсе областной столицы.

Наконец, анализ метаданных архива позволяет сказать, что сайт больше двух других опирается на визуальную презентацию контента, о чем свидетельствует больший относительный вес изображений формата `jpeg`.

Подробнее с метаданными для разных типов данных можно ознакомиться в файлах `digital_meta.jsonl` и `headers.jsonl`.
