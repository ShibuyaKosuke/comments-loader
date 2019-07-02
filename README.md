# Laravel table comments loader

[![Build Status](https://travis-ci.org/diplodocker/comments-loader.svg?branch=master)](https://travis-ci.org/diplodocker/comments-loader)
[![Made for Laravel](https://img.shields.io/badge/made%20for-laravel-orange.svg?style=flat&logo=Laravel&logoColor=fff)](https://laravel.com/)
![PHP from Packagist](https://img.shields.io/packagist/php-v/diplodocker/comments-loader.svg?color=8a92bb&logo=php&logoColor=fff)

### Why should I use a package?
[Because](https://github.com/laravel/framework/pull/17209#issuecomment-271296396)

### Install
* Install [laravel](https://laravel.com/docs/master/installation) =)
* `composer require diplodocker/comments-loader`

### Use class
```php
<?php

use Diplodocker\CommentsLoaderMigration;

class SomeMigrationFileName extends CommentsLoaderMigration
{
    public $comments = [
        'users' => 'Users table',
        'documents' => 'Documents table',
        ...
    ];

```
### Or use trait
```php
<?php

use Diplodocker\Concerns\CommentsLoader;
use Illuminate\Database\Migrations\Migration;

class SomeMigrationFileName extends Migration
{
    // use trait
    use CommentsLoader;

    public $comments = [
        'users' => 'Users table',
        'documents' => 'Documents table',
        ...
    ];

    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        // your code here
        $this->loadTableComments();
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        // your code here
    }

```
