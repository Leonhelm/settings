## Настройки для WebStorm после установки

#### Импортируем настройки из файла `webstorm.zip`
```
File > Import Settings...
```

#### Устанавливаем доступ по программе `Early Access Preview`:
* Переходим `File > Settings... > Apperance & Behavior > System Settings > Updates`
* Устанавливаем `Automatically check updates for Early Access Preview`

#### Настраиваем автоисправление `eslint` по `ctrl+s`
* Переходим `File > Settings... > Tools > File Watchers > Add
* Выбираем `<custom>`
* Устанавливаем:
* * Name: `ESlint fix`
* * File type: `any`
* * Создаём новый Scope:
* * * Выбираем `Shared`
* * * Name: `JS+TS+JSON`
* * * Pattern: `file:*.js||file:*.jsx||file:*.ts||file:*.tsx||file:*.json`
* * Выбираем `JS+TS+JSON` в поле Scope
* * Program: `./node_modules/.bin/eslint`
* * Arguments: `--fix $FilePath$`
* * Output paths to refresh: `$FileDir$`
* * Auto-save edited files to trigger the watcher: `false`
* * Trigger the watcher on external changes: `false`
