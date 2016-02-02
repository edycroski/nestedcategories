# nestedcategories

A Laravel 5 package for adding one or more types of category hierarchies to a website.

e.g. a hierarchy for blog categories and another for product categories

This is a Laravel 5 reimplementation of [Laravel 4 Categories](https://github.com/FbF/Laravel-Categories)

## Comes with

* Migration for the `categories` table
* Category Model (that extends Baum/Node so you can use all the handy methods from this excellent nested set implementation)
* Seed for building the root nodes, one for each type of hierarchy, specified in your config file

## Installation

Add these lines to your composer.json file:

```
    "require": {
        "delatbabel/nestedcategories": "~1.0"
    },
```

Once that is done, run the composer update command:

```
    composer update
```

Alternatively just run this command:

```
    composer require delatbabel/nestedcategories
```

### Register Service Provider

After composer update completes, add this line to your config/app.php file in the 'providers' array:

```
    Delatbabel\NestedCategories\NestedCategoriesServiceProvider::class
```

### Publish the Migrations

Publish the migrations

```
    php artisan vendor:publish
```

Run the migration

```
    php artisan migrate
```

Ensure the categories `types` are set correctly in the seeder file.  You can initialise this to
whatever you like.

### Run the Seeders

Run the seed (this will create root nodes for each of your category `types`)

```
    php artisan db:seed --class="CategoriesTableBaseSeeder"
```