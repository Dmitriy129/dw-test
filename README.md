# dw-test

## Script 1 
### Обязательно указать:

```
env.PR_BOT_CONFIG_PATH - название директории с конфигом. Пример: bot_config
env.MOODLE_ACCESS_TOKEN - токен для мудл. Для удобства и безопасности храню его в Settings>Secrets>Actions
```
###  Конфиг "PR_BOT_CONFIG_PATH/script1.json"
> пример bot_config/script1.json

``` json
[
    {
        "prRegex": "^\\w*_(lr1)$", // регулярка для выбора конфига для определнного pr
        "courseId": 47,
        "cmId": 1553
    },
    ...
]
```




## Script 2
### Обязательно указать:

```
env.PR_BOT_CONFIG_PATH - название директории с конфигом. Пример: bot_config
env.MOODLE_ACCESS_TOKEN - токен для мудл. Для удобства и безопасности храню его в Settings>Secrets>Actions
COURSE_ID - id курса
CM_ID - id модуля курса
GITHUB_PR_REGEX - регулярка для определения подходящих pr
```


## Config
``` json
{
    "github": {
        "gradeLabel": { // script 1
            "defaultTemplate": "#Moodle", // Добавляется в начало текста метки. Служит для отличия от остальных меток, которые не надо трогать.
            "defaultColor": "c4c", // цвет по умолчанию
            "config": [
                [
                    [0, 30], // % = raw/max  [from %, to %]
                    {
                        "color": "ff3d00", // цвет метки
                        "template": "Не сдали ({raw}/{max})", // текст метки
                        "description": "можно написать, видно при наведени и в настройках" // описание метки
                    }
                ],
                ...
            ]
        },
        "accessLabel": { // script 2
            "defaultTemplate": "#Moodle",
            "defaultColor": "c4c",
            "config": [
                 [
                    [0, 30], // % = raw/max  [from %, to %]
                    {
                        "color": "ff3d00", // цвет метки
                        "template": "Не сдали ({raw}/{max})", // текст метки
                        "description": "можно написать, видно при наведени и в настройках" // описание метки
                    }
                ],
                ...
            ]
        }
    },
    "moodle": {
        "baseUrl": "http://e.moevm.info" // url 
    },
    "googleSheet": {// пример https://docs.google.com/spreadsheets/d/1-KENToVk8vYABspbj-7gUsojEO9lFMzffeNVVACqPEQ/edit#gid=0
        "id": "1-KENToVk8vYABspbj-7gUsojEO9lFMzffeNVVACqPEQ", 
        "headers": { // Заголовки таблицы
            "fio": "ФИО",
            "email": "Email",
            "github": "github",
            "username": "username",
            "group": "Группа"
        }
    }
}

```