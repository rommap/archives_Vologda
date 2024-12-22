# Архив сайта администрации города Вологды


Архив сайта вместе с файлами `log` (*к сожалению, утрачен*) и `cdx` со всеми ссылками, а также база данных в формате `db` находятся в облачном хранилище Google Disk по [ссылке](https://drive.google.com/drive/folders/1w2z-_vhX5kBnEy7U1ylxl9p6ksaSzDuE).

## Результаты
![](https://github.com/rommap/archives_Vologda/blob/main/vologda.gosuslugi.ru/Replay_Vologda.png)

Воспроизведение содержимого архива в `ReplayWeb.page`, как и в случае с другими архивируемыми сайтами, помогает удостовериться в корректности полученных данных. Здесь также не воспроизводятся фрагменты кода `javascript` и не открываются ссылки на сторонние ресурсы - к примеру, на сайты туристических агентств.

## Извлечение метаданных
Метаданные анализировались с помощью следующих команд из библиотеки metawarc:
+ `analyze` - возвращает статистику с абсолютным и относительным числом и весом файлов каждого из типов, представленных в архиве
+ `metadata` - извлекает метаданные каждого файла архива в отдельный файл `digital_meta.jsonl`
+ `export` - извлекает заголовки HTTP, заголовки WARC или текстовое содержимое из архива в файл `headers.jsonl`

## Описание метаданных
`metawarc analyze vologda.gosuslugi.ru.warc.gz`

```
mimes                                                                      files         size          share
-----------------------------------------------------------------------  -------  -----------  -------------
application/pdf                                                             1414   5449877198   53.3933     
text/html                                                                  13586   3261462735   31.953      
image/jpeg                                                                  1916    467062892    4.57589    
application/zip                                                              185    369883479    3.6238     
application/vnd.openxmlformats-officedocument.wordprocessingml.document     1233    157884344    1.54682      
application/msword                                                          1614    156180685    1.53013      
application/vnd.openxmlformats-officedocument.wordprocessingml.document     1233    157884344    1.54682      
application/vnd.openxmlformats-officedocument.wordprocessingml.document     1233    157884344    1.54682      
application/msword                                                          1614    156180685    1.53013      
image/png                                                                    365    136941526    1.34164      
video/mp4                                                                      9    134448965    1.31722      
video/mp4                                                                      9    134448965    1.31722      
application/rtf                                                               72     29972517    0.293645     
application/vnd.ms-excel                                                     163     19355283    0.189627     
application/octet-stream                                                      41      9618041    0.0942294    
application/octet-stream                                                      41      9618041    0.0942294    
text/css                                                                      32      6280587    0.0615319    
image/svg+xml                                                                110      2846441    0.027887     
text/css                                                                      32      6280587    0.0615319    
image/svg+xml                                                                110      2846441    0.027887     
text/xml                                                                       9      1521676    0.0149081    
application/javascript                                                        23      1269644    0.0124389    
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet             26      1269026    0.0124328    
image/svg+xml                                                                110      2846441    0.027887     
text/xml                                                                       9      1521676    0.0149081    
application/javascript                                                        23      1269644    0.0124389    
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet             26      1269026    0.0124328    
text/xml                                                                       9      1521676    0.0149081    
application/javascript                                                        23      1269644    0.0124389    
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet             26      1269026    0.0124328    
application/vnd.ms-fontobject                                                  6       520784    0.0051022    
application/vnd.ms-fontobject                                                  6       520784    0.0051022    
font/woff                                                                      6       346236    0.00339213   
font/woff2                                                                     3       166480    0.00163103   
image/webp                                                                     2        91460    0.000896047  
application/vnd.oasis.opendocument.spreadsheet                                 2        39165    0.000383705  
image/gif                                                                      1         8842    8.66264e-05  
text/plain                                                                     1          704    6.89719e-06  
#total                                                                     20819  10207048710  100
```

В отличие от сайта мэрии Череповца, здесь данные формата `pdf` занимают наибольшое место в архиве, а формат `zip`, наоборот, почти не используется.

Кроме этого, на Вологодском сайте и в относительных, и в абсолютных числах больший вес занимает разметка `html`, а фотографии `jpeg` - меньший также и в относительных, и в абсолютных показателях. Это, вероятно, говорит о том что создатели сайта в презентации контента больше внимания уделяют организации текста, нежели размещению картинок.

Наконец, можно обратить внимание на то, что количесвто данных на `javascript` одинаково на обоих городских сайтах. Это значит, что наличие этих вставок обусловлено исключительно единым шаблоном сайтов, выполненных в стилистике Госуслуг.

Подробнее с метаданными для разных типов данных можно ознакомиться в файлах `digital_meta.jsonl` и `headers.jsonl`.
