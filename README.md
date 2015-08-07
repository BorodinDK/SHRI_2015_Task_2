Работа с API
========

Ссылка на рабочий пример – [borodindk.github.io/SHRI_2015_Task_2](http://borodindk.github.io/SHRI_2015_Task_2)

### Исправление ошибки

Ошибка заключается в том что переменная request внутри функции callback берется из глобальной области видимости, а она там равна 3, так как цикл завершил свою работу до вызова коллбеков.

Чтобы исправить эту ошибку можно привязать ```request``` к функции ```callback```
```javascript
callback.request = request;

```
а в самой функции заменить ```responses[request] = result;``` на ```responses[cb.request] = result;``` и дать безымянной функции имя cb ```var callback = function cb(error, result) {}```.

### Добавление диалога с пользователем
Ввод данных реализовал при помощи ```window.prompt``` а вывод сделал через ```window.alert```.