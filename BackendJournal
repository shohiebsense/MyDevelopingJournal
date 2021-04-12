# MyWebDevelopingJournal

## Yii

### Remove index.php and controller name in routing / url

> 1. Add the .htaccess file or modify
```htaccess
RewriteEngine On
#RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)\?*$ index.php/$1 [L,QSA]
```

> 2. Modify the main.php in protected/config/main.php
```php
'urlManager' => array(
            'urlFormat' => 'path',
            'showScriptName' => false, //to remove r=controllerName
            'caseSensitive' => false,
            'routeVar' => 'route',
            'rules' => array(
                '' => 'controllerName/index',
                'get<action>' => 'controllerName/<action>',
                'insert<action>' => 'controllerName/<action>',
                // '<controller:\w+>/<id:\d+>' => '<controller>/view',
                // '<controller:\w+>/<action:\w+>/<id:\d+>' => '<controller>/<action>',
                // '<controller:\w+>/<action:\w+>' => '<controller>/<action>',
            ),
        ),
```
