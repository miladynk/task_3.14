[вернуться к содержанию](/readme.md)

## .gitignore
---

Иногда нам не надо, чтобы Git отслеживал все файлы в репозитории, ведь в их число могут входить: 
- файлы с конфиденциальной информацией;
- огромные бинарные файлы; 
- специфичные файлы;
- файлы сборок, генерируемые после каждой компиляции. 

Для игнорирования предусмотрен файл `.gitignore`, где отмечаются файлы для игнорирования. 

К шаблонам в файле `.gitignore` применяются следующие правила:
* Пустые строки, а также строки, начинающиеся с `#`, игнорируются.
* Стандартные шаблоны являются глобальными и применяются рекурсивно для всего дерева каталогов.
* Чтобы избежать рекурсии используйте символ слеш (`/`) в начале шаблона.
* Чтобы исключить каталог добавьте слеш (`/`) в конец шаблона.
* Можно инвертировать шаблон, использовав восклицательный знак (`!`) в качестве первого символа.

Glob-шаблоны представляют собой упрощённые регулярные выражения, используемые командными интерпретаторами. 
- Символ (`*`) соответствует 0 или более символам; 
- последовательность [abc] — любому символу из указанных в скобках (в данном примере a, b или c); 
- знак вопроса (`?`) соответствует одному символу; 
- квадратные скобки, в которые заключены символы, разделённые дефисом (`[0-9]`), соответствуют любому символу из интервала (в данном случае от 0 до 9). 
- Мы также можем использовать две звёздочки, чтобы указать на вложенные каталоги: `a/**/z` соответствует a/z, a/b/z, a/b/c/z, и так далее.

Вот ещё один пример файла `.gitignore`:

```bash =
# Исключить все файлы с расширением .a
*.a

# Но отслеживать файл lib.a даже если он подпадает под исключение выше
!lib.a
	
# Исключить файл TODO в корневом каталоге, но не файл в subdir/TODO

/TODO

# Игнорировать все файлы в каталоге build/
build/

# Игнорировать файл doc/notes.txt, но не файл doc/server/arch.txt
doc/*.txt

# Игнорировать все .txt файлы в каталоге doc/
doc/**/*.txt
```
