## miktex (basic ~250mb)
  https://miktex.org/download
  
  скачать и установить
  
### MikTeX Console (есть в стартовом меню)
  - Updates -> Check for updates -> Update now
  - Packages -> Update DB -> "latex" в фильтр -> установить, если не установлены
      - latexmk
      - latexindent

## Strawberry Perl (для latexmk и latexindent)
  https://strawberryperl.com/
  
  скачать и установить 64bit
  


## VSCode
[Страница для скачивания](https://code.visualstudio.com/)

- Скачать, установить, запустить

- Перейти в Extensions
  
- Установить LaTeX Workshop
    
- Установить LaTeX Utilities
    
- Выключить или удалить все остальные, относящиеся к LaTeX

После этого должна работать компиляция (в том числе автоматически при сохранении файла), обычные (не "на лету") сниппеты, и остальные [фишки LaTeX Workshop](https://github.com/James-Yu/LaTeX-Workshop#features-taster) (например, просмотр pdf во вкладке VSCode с прямым и обратным поиском) и некоторые [фишки LaTeX Utilities](https://github.com/tecosaur/LaTeX-Utilities/#features) (например, вставка таблиц из буфера обмена, скопированных из Excel)

### Навигация в VSCode
При нажатии 'Ctrl+P' откроется строка поиска файлов (открытых и тех что есть в рабочей папке)
- Если нажать `Ctrl+P` и ввести `@` (или нажать `Ctrl+Shift+O`), то выведется содержание открытого файла, и там можно перейти к интересующей главе или метке
- Если нажать `Ctrl+P` и ввести `>` (или нажать `Ctrl+Shift+P`), то появится список всех доступных команд. Попробуйте ввести latex и посмотреть команды, которые предоставляют расширения LaTeX Workshop и LaTeX Utilities

### Настройка latexindent (форматтер)
Запускаем PowerShell и выполняем три команды (этих двух пакетов достаточно при актуальных на 16.01.2021 версии программ и Windows). Если установили Perl не по стандартному пути, измените путь

  ```cd C:\Strawberry\perl\bin```

  ```cpan -f -i Log::Log4perl```
  
  ```cpan -f -i Log::Dispatch::File```

После этого должны заработать функции `Format document` и `Format selection` в контекстном меню VSCode. С настройками по умолчанию latexindent расставляет табуляцию и пробелы внутри таблиц для лучшей читаемости. 

### Настройка live snippets
LaTeX Utilities предоставляет возможность пользоваться live snippets, это автозамены, срабатывающие при обнаружении определенного кода автоматически. Описание, примеры стандартных, а также как их включить, [тут](https://github.com/tecosaur/LaTeX-Utilities/wiki/Live-Snippets#the-defaults)

- Заходим в настройки (Ctrl+,)
- Вводим live reformat в поиск (курсор в поле ввода уже должен стоять)
- Отмечаем галку напротив Live Reformat: Enabled
- Перезапускаем VSCode

Кроме примеров по ссылке выше, среди стандартных сниппетов есть 
- сниппеты, вставляющие пробелы, когда вы пишете оператор, или что-то после оператора (например `1+ -> 1 +`  и `=2 -> = 2`);
- сниппеты, с помощью которых при нажатии пробела несколько раз в математическом режиме, автоматически вставляются перебираются следующие команды: `\,`,`\:`, `\;` и т.д.

В моём файле добавлены некоторые сниппеты, аналогичные тем, что можно найти в [этой статье](https://castel.dev/post/lecture-notes-1/):
- сниппеты для быстрого ввода математематического окружения
  - mk для внутристрочного окружения `\( \)`
  - dm для вынесенной формулы `\[ \]` (смотрите также команду `Toggle between \[...\] and \begin{}...\end{}`)
  - `__ -> _{}` с курсором между скобками
  - `^^ -> ^{}`
  - `... -> \ldots`
  - `eps -> \varepsilon`
  - `cc -> \subseteq`
  - `tt -> \text{}` в мат. режиме
  - `ooo -> \infty`
  - `OO -> \varnothing`
  - `norm -> \unlhd`
  - `uu -> \cup`
  - `nn -> \cap`
  - аналогичные стандартным для `bar` (`\overline`) и hat, только для `\mathrm` и `\mathfrak` (например `Oqmrm` заменится на `\mathrm{Oq}`, `Xfrak` на `\mathfrak{X}`)
  - и ещё несколько более специализированных, так что их возможно, будет удобнее удалить.

Для редактирования live snippets используйте команду `Edit Live Snippets File`

