Yii2 SEO Management
===================
A full SEO manament system for Yii2.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist linchpinstudios/yii2-seo "*"
```

or add

```
"linchpinstudios/yii2-seo": "*"
```

to the require section of your `composer.json` file.

<h5>3) Run Migrations</h5>
<strong>For Blog</strong>
```
./yii migrate/up --migrationPath=@vendor/linchpinstudios/yii2-seo/migrations
```


Usage
-----

Setup beforeAction in controllers you want to use SEO

```public function beforeAction($action)
    {
        if (parent::beforeAction($action)) {
            $seoMetaTags = New \linchpinstudios\seo\models\Seo;
            $seoMetaTags->run();
            return true;  // or false if needed
        } else {
            return false;
        }
    }```

To access the module, you need to add this to your application configuration:

```<?php
    ......
    'modules' => [
        'seo' => [
            'class' => 'linchpinstudios\seo\Module',
        ],
    ],
    ......```