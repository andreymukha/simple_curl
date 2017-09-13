Simple Curl
=====================
Лёгкая оёбртка для запросов Curl.

### Использование

```php
//Инициализация нового экземпляра класса
$curl = curl::app('http://site.ru/');
```

### Установка опций
//Установка своих параметров, например:
$curl->set(CURLOPT_HEADER, true);

### Предустановленные параметры:
```php
$curl->setHeader(true)
->setReferer('http://site.ru/')
->setFollow(true)
->setUagent('Mozilla/5.0 (Windows NT 6.1; WOW64; rv:45.0) Gecko/20100101 Firefox/45.0')
->setCookie('cookie')
->setDisableSSL()

//Если хотите указать конкретный прокси
->setProxy('192.168.1.1:8080')

//Использует автоматический сервис для выдачи прокси
->setProxy('auto')

//Для POST запросов
->setQuery('POST', $data_array);

//Можно для следующего запроса переключиться на другой тип
->setQuery('GET');
```

### Отправка запроса
```php
$data = $curl->request('page/1');
 
//Если надо конвертировать данные из одной кодировки в другую
$data = $curl->request('page/1', 'windows-1251', 'utf-8'); 
```