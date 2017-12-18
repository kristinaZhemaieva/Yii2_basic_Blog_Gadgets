yii2-blog
=========

Yii2 blog module
Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist pendalf89/yii2-blog "*"
```

or add

```
"pendalf89/yii2-blog": "*"
```

to the require section of your `composer.json` file.

Apply migration
```sh
yii migrate --migrationPath=vendor/pendalf89/yii2-blog/migrations
```

Configuration:

```php
'modules' => [
    'blog' => [
        'class' => 'pendalf89\blog\Module',
        // This option automatically translit entered titles 
        // from russian symbols to english on fly. Default false.
        'autoTranslit' => true, 
        // Some options for CKEditor. Default custom options.
        'editorOptions' => [],
        // callback function for create post view url. Have $model argument.
        'viewPostUrlCallback' => function($model) {
                return '/' . $model->alias;
            },
    ],
],
```

Don't forget configure [PendalF89/yii2-filemanager](https://github.com/PendalF89/yii2-filemanager) extension.
