# Laravel 5.x Scaffold Generator

Laravel Scaffold Generator, for Laravel 5.3.

## Install

### Step 1: Install Through Composer

```
composer config repositories.laravel5-generator vcs https://github.com/jimanx2/laravel5-generator
composer require laravel5-generator:dev-master
```

### Step 2: Add the Service Provider

Open `/config/app.php` and, to your **providers** array, add:

```
$providers = [
...
     \Summerblue\Generator\GeneratorsServiceProvider::class,
...
];
```

### Step 3: Run Artisan!

You're all set. Run `php artisan` from the console, and you'll see the new commands `make:scaffold`.

## Examples

Use this command to generator scaffolding of **Project** in your project:

> php artisan make:scaffold Projects --schema="name:string:index,description:text:nullable,subscriber_count:integer:unsigned:default(0)"

This command will generate:

```
$ php artisan make:scaffold Projects --schema="name:string:index,description:text:nullable,subscriber_count:integer:unsigned:default(0)"


----------- scaffolding: Project -----------

+ ./database/migrations/2017_04_17_065656_create_projects_table.php
+ ./database/factories/ModelFactory.php
+ ./database/seeds/ProjectsTableSeeder.php
+ ./database/seeds/DatabaseSeeder.php (Updated)
x ./app/Models/Model.php (Skipped)
+ ./app/Models/Project.php
+ ./app/Http/Controllers/ProjectsController.php
x ./app/Http/Requests/Request.php (Skipped)
+ ./app/Http/Requests/ProjectRequest.php
+ ./app/Observers/ProjectObserver.php
+ ./app/Providers/AppServiceProvider.php (Updated)
x ./app/Policies/Policy.php
+ ./app/Policies/ProjectPolicy.php
+ ./app/Providers/AuthServiceProvider.php (Updated)
+ ./routes/web.php (Updated)

--- Views ---
   + create_and_edit.blade.php
   + index.blade.php
   + show.blade.php
x ./resources/views/error.blade.php
Migrated: 2017_04_17_065656_create_projects_table

----------- -------------------- -----------
-----------   >DUMP AUTOLOAD<    -----------
```

## Explain

Generate the following:

- Migration
- Seed, add ModelFactory entry, and DatabaseSeeder entry
- Base Model class, Model and helper trait
- Resource Controller
- Base FormRequest class and StoreRequest, UpdateRequest
- Policy and Policy base class, auto register AuthServiceProvider class
- Update routes file to register resource route
- Add error page view
- Create and Edit action share the same view

## Future Plan

- API
- Admin
- Auto fill FormRequest rule
- Auto fill ModelFactory filed

## Screenshot

![file](https://cloud.githubusercontent.com/assets/324764/22488519/7466a638-e84d-11e6-8201-99ad377d6270.png)

## Thinks to
- [laralib/l5scaffold](https://github.com/laralib/l5scaffold)
"# laravel5-generator" 
