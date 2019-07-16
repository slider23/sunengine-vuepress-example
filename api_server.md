# API сервера

## /api/Menu/GetAllMenuItems

Получение всех пунктов главного меню.

Реквест:

```
POST /api/Menu/GetAllMenuItems
```

Пример респонса (c sunengine.site):

```
[{
    "id": 1,
    "parent": null,
    "parentId": null,
    "name": "Root",
    "title": "Root",
    "subTitle": null,
    "routeName": null,
    "routeParamsJson": null,
    "exact": false,
    "settingsJson": null,
    "cssClass": null,
    "externalUrl": null,
    "isSeparator": false,
    "sortNumber": 1,
    "icon": null,
    "customIcon": null,
    "isHidden": false
}, {
    "id": 2,
    "parent": null,
    "parentId": 1,
    "name": "DocsMenu",
    "title": "Документация",
    "subTitle": null,
    "routeName": null,
    "routeParamsJson": null,
    "exact": false,
    "settingsJson": null,
    "cssClass": null,
    "externalUrl": null,
    "isSeparator": false,
    "sortNumber": 2,
    "icon": "fas fa-bars",
    "customIcon": null,
    "isHidden": false
}, {
    "id": 12,
    "parent": null,
    "parentId": 20,
    "name": null,
    "title": "О проекте",
    "subTitle": null,
    "routeName": "cat-Texts-mat",
    "routeParamsJson": {
        "idOrName": "about"
    },
    "exact": false,
    "settingsJson": null,
    "cssClass": null,
    "externalUrl": null,
    "isSeparator": false,
    "sortNumber": 5,
    "icon": "fas fa-info-circle",
    "customIcon": null,
    "isHidden": false
}, {
    "id": 11,
    "parent": null,
    "parentId": 2,
    "name": null,
    "title": "Требования для запуска",
    "subTitle": "Prerequisites",
    "routeName": "articles-Docs-mat",
    "routeParamsJson": {
        "idOrName": "7"
    },
    "exact": false,
    "settingsJson": null,
    "cssClass": null,
    "externalUrl": null,
    "isSeparator": false,
    "sortNumber": 9,
    "icon": null,
    "customIcon": null,
    "isHidden": false
}, {
    "id": 9,
    "parent": null,
    "parentId": 2,
    "name": null,
    "title": "Запуск SunEngine",
    "subTitle": "В development режиме",
    "routeName": "articles-Docs-mat",
    "routeParamsJson": {
        "idOrName": "5"
    },
    "exact": false,
    "settingsJson": null,
    "cssClass": null,
    "externalUrl": null,
    "isSeparator": false,
    "sortNumber": 10,
    "icon": null,
    "customIcon": null,
    "isHidden": false
}, {
    "id": 33,
    "parent": null,
    "parentId": 2,
    "name": null,
    "title": "Конфигурация",
    "subTitle": "Директория конфигурации",
    "routeName": "articles-Docs-mat",
    "routeParamsJson": {
        "idOrName": "38"
    },
    "exact": false,
    "settingsJson": null,
    "cssClass": null,
    "externalUrl": null,
    "isSeparator": false,
    "sortNumber": 33,
    "icon": null,
    "customIcon": null,
    "isHidden": false
}]
```

## /api/Materials/Get

Получение материала по {id}

Запрос:

```
POST /api/Materials/Get

multipart/form-data
idOrName: {id}
```

Пример ответа:

```
{
    "name": null,
    "id": 38,
    "title": "Файлы конфигурации",
    "subTitle": null,
    "text": "<h4>Использование директории конфигурации</h4><div>Директории конфигурации при запуске выбирается опцией config:</div><div>Директории конфигурации по умолчанию смотрятся в папке&nbsp;<i>\"/SunEngine/SunEngine.Cli/\", если надо использовать конфигурацию из другого места</i>&nbsp;- указывайте полный путь, или относительный через<i> \"..\". </i>Директория конфигурации либо <i>\"Config\"</i> - по умолчанию, либо должна заканчиваться на суффикс <i>\".Config\"</i>, который автоматически добавляется к опции.<br><div><br></div><div><b>Примеры:</b></div><div><i>\"dotnet SunEngine.dll server\"</i> - запуск с директорией по-умолчанию <i>\"Config \"</i></div><div><i>\"dotnet SunEngine.dll server config:MySite</i>\" - запуск с директорией <i>\"MySite.Config\"</i> (суффикс <i>\".Config\"</i> добавляется автоматически)<br></div><div><i>\"dotnet SunEngine.dll server config:MySite.Config\"</i> - то же самое, <i>\"MySite.Config\"</i><br></div><div><i><br></i></div><div>Команда config действует так же и для всех других для команд: <i>init, migrate, seed</i>..., например:</div><div><i>\"dotnet SunEngine.dll migrate init seed config:MySite\"</i><br></div><div><br></div><div>Для того что бы ваш конфиг не перезатирался после обновления с GitHub просто скопируйте<i> \"Config\"</i> в другую папку, суффикс <i>\".Config\"</i> обязателен, например <i>\"my_site.com.Config\"</i>.</div><div>Можно использовать префикс<i> \"local.\"</i> в этом случае эта папка не будет пушится в GitHub, так как приставка <i>\"local\"</i> прописана в <i>\".gitignore\":</i></div><div><pre>[Ll]ocal.*<br>[Ll].*</pre><div><span style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\">Например:</span><i style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\"> \"local.</i><i style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\">my_site.com.Config\" </i><span style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\">или</span><i style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\">&nbsp;</i><i style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\">&nbsp;\"l.</i><i style=\"font-family: Roboto, -apple-system, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; white-space: normal;\">my_site.com.Config\" .</i></div></div><h4>Содержание директории конфигурации</h4></div><h5>Только для стартовой инициализации базы, команда init</h5><div><i>\"Categories\"</i> - создание и настройка категорий, только для команды init, далее на рабочем сервере категории настраиваются через админку</div><div><i>\"Menu\"</i>&nbsp; - создание и настройка меню сайта, только для команды init, далее на рабочем сервере меню настраиваются через админку</div><div><i>\"Users.json\" </i>- создание пользователей для init<br></div><div><i>\"Roles.json\"</i> - создание ролей пользователей и их прав для init</div><h5>Постоянные настройки</h5><div><i>\"DataBaseConnection.json\" </i>- подключение к базе данных</div><div><div><i>\"SunEngine.json\" </i>- основные настройки сайта</div></div><div><i>\"Sanitizer.json\"</i> - настройка очистки текстов от запрещённых тегов, атрибутов, css классов, стилей css, доменов в iframe.</div><div><br></div>",
    "authorName": "Dmitrij Polianin",
    "authorId": 1,
    "authorLink": "1",
    "authorAvatar": "67/CFUffWb3tkRlGOUGHMPp.jpg",
    "commentsCount": 0,
    "publishDate": "2019-07-08T17:32:11.928288Z",
    "editDate": "2019-07-09T07:46:24.451854Z",
    "categoryName": "Docs",
    "isCommentsBlocked": true,
    "isHidden": false,
    "isDeleted": false,
    "tags": ["config", "конфигурация", "настройка"]
}
```

## /api/Comments/GetMaterialComments

Получение комментариев к материалу по его {id}

Запрос:

```
POST /api/Comments/GetMaterialComments

multipart/form-data
materialId: {id}
```

Пример ответа:

```
[{
    "id": 28,
    "authorId": 1,
    "authorName": "Dmitrij Polianin",
    "authorLink": "1",
    "authorAvatar": "67/CFUffWb3tkRlGOUGHMPp.jpg",
    "text": "<div><img class=\"text-img\" src=\"https://sunengine.site/UploadImages/114/rOZB5jIPZ1WHsYedH95d.jpg\"></div>",
    "publishDate": "2019-07-06T17:11:13.350622Z",
    "editDate": "2019-07-06T17:11:13.350622Z",
    "isDeleted": false
}, {
    "id": 29,
    "authorId": 1,
    "authorName": "Dmitrij Polianin",
    "authorLink": "1",
    "authorAvatar": "67/CFUffWb3tkRlGOUGHMPp.jpg",
    "text": "<div><img src=\"https://sunengine.site/UploadImages/113/qc4MFQQ1xyEyAagS5pjI.jpg\"></div>",
    "publishDate": "2019-07-08T16:40:29.771037Z",
    "editDate": "2019-07-08T16:40:29.771037Z",
    "isDeleted": false
}, {
    "id": 30,
    "authorId": 1,
    "authorName": "Dmitrij Polianin",
    "authorLink": "1",
    "authorAvatar": "67/CFUffWb3tkRlGOUGHMPp.jpg",
    "text": "<div><img src=\"https://sunengine.site/UploadImages/71/GiSkHpXEVrazyuDQt7jD.jpg\"></div>",
    "publishDate": "2019-07-08T17:48:33.844441Z",
    "editDate": "2019-07-08T17:48:33.844441Z",
    "isDeleted": false
}]
```

## /api/Categories/GetAllCategoriesAndAccesses

Требуется описание.

Запрос:

```
POST /api/Categories/GetAllCategoriesAndAccesses
```

Пример ответа:

```{
    "id": 1,
    "name": "Root",
    "title": "Root",
    "sortNumber": 1,
    "materialsSubTitleInputType": 0,
    "isMaterialsNameEditable": false,
    "isMaterialsContainer": false,
    "isHidden": false,
    "categoryPersonalAccess": {
        "materialAndCommentsRead": true
    },
    "subCategories": [{
        "id": 2,
        "name": "Blog",
        "title": "Блог",
        "sortNumber": 2,
        "layoutName": "Blog",
        "materialsSubTitleInputType": 0,
        "isMaterialsNameEditable": false,
        "isMaterialsContainer": true,
        "isHidden": false,
        "categoryPersonalAccess": {
            "materialAndCommentsRead": true
        }
    }, {
        "id": 4,
        "name": "Texts",
        "title": "Тексты сайта",
        "sortNumber": 4,
        "layoutName": "Articles",
        "materialsSubTitleInputType": 0,
        "isMaterialsNameEditable": true,
        "isMaterialsContainer": true,
        "isHidden": false,
        "categoryPersonalAccess": {
            "materialAndCommentsRead": true
        }
    }, {
        "id": 12,
        "name": "SunEngine",
        "title": "SunEngine",
        "sortNumber": 5,
        "materialsSubTitleInputType": 0,
        "isMaterialsNameEditable": false,
        "isMaterialsContainer": false,
        "isHidden": false,
        "categoryPersonalAccess": {
            "materialAndCommentsRead": true
        },
        "subCategories": [{
            "id": 3,
            "name": "Docs",
            "title": "Документация",
            "sortNumber": 3,
            "layoutName": "Docs",
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 17,
            "name": "Video-SE",
            "title": "Видео",
            "sortNumber": 17,
            "layoutName": "Articles",
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }]
    }, {
        "id": 13,
        "name": "HappyDeveloper",
        "title": "Happy Developer",
        "sortNumber": 12,
        "materialsSubTitleInputType": 0,
        "isMaterialsNameEditable": false,
        "isMaterialsContainer": true,
        "isHidden": false,
        "categoryPersonalAccess": {
            "materialAndCommentsRead": true
        },
        "subCategories": [{
            "id": 14,
            "name": "Video-HD",
            "title": "Видео",
            "sortNumber": 14,
            "layoutName": "Articles",
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 15,
            "name": "Articles-HD",
            "title": "Статьи",
            "sortNumber": 15,
            "layoutName": "Articles",
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }]
    }, {
        "id": 5,
        "name": "Forum",
        "title": "Forum",
        "sortNumber": 13,
        "layoutName": "Forum1",
        "materialsSubTitleInputType": 0,
        "isMaterialsNameEditable": false,
        "isMaterialsContainer": false,
        "isHidden": false,
        "categoryPersonalAccess": {
            "materialAndCommentsRead": true
        },
        "subCategories": [{
            "id": 6,
            "name": "General",
            "title": "Основной",
            "sortNumber": 6,
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 10,
            "name": "UI",
            "title": "Интерфейс",
            "header": "<div style=\"text-align: center\">Предложения по улучшению юзабилити и интерфейса SunEngine</div>",
            "sortNumber": 7,
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 7,
            "name": "Q&A",
            "title": "Вопросы и ответы",
            "sortNumber": 8,
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 8,
            "name": "Help",
            "title": "Помощь",
            "sortNumber": 9,
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 9,
            "name": "Talk",
            "title": "Общение",
            "sortNumber": 10,
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }, {
            "id": 16,
            "name": "HappyDeveloper-Forum",
            "title": "Счастливый разработчик",
            "sortNumber": 16,
            "materialsSubTitleInputType": 0,
            "isMaterialsNameEditable": false,
            "isMaterialsContainer": true,
            "isHidden": false,
            "categoryPersonalAccess": {
                "materialAndCommentsRead": true
            }
        }]
    }]
}
```
