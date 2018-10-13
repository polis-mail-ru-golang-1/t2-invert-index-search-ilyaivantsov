# Поиск релевантного файла

Утилита выполняющая поиск указанной фразы по указанным файлам. На вход принимает список файлов и текст фразы. В начале работы производит индексацию файлов, строит по каждому [обратный индекс](https://ru.wikipedia.org/wiki/Инвертированный_индекс). Затем сравнивает файлы по наилучшему совпадению содержимого с поисковой фразой. Выводит на экран файлы, где были найдены токены из поисковой фразы в порядке наилучшего соответствия. Наилучшее соответствие - все токены из поисковой фразы встретились в файле наибольшее количество раз. Если ни одного токена из фразы не найдено в файле, выводить его не следует.

При разработке следует разбить логику приложения на отдельные пакеты. Разрешается использовать сторонние пакеты для реализации дополнительного функционала, на усмотрение.

Файлы для индексации вводятся аргументами при запуске бинарного файла. Например: `./search -s file1.txt,file2.txt`. Либо без ключей аргументов: `./search file1.txt file2.txt`. Поисковая фраза вводится из stdin (предпочтительно) или отдельным аргументом.

Результат выводится в консоль в виде:
```
- file1.txt; совпадений - 2
- file2.txt; совпадений - 1
```

В случае ошибки чтения файла, работу следует прервать. Можно считать, что текст содержит символы только из ASCII.
