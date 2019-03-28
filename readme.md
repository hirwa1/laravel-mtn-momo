## Laravel MTM Momo API Integration

[![Total Downloads](https://poser.pugx.org/bmatovu/laravel-mtn-momo/downloads)](https://packagist.org/packages/bmatovu/laravel-mtn-momo)
[![Latest Stable Version](https://poser.pugx.org/bmatovu/laravel-mtn-momo/v/stable)](https://packagist.org/packages/bmatovu/laravel-mtn-momo)
[![License](https://poser.pugx.org/bmatovu/laravel-mtn-momo/license)](https://packagist.org/packages/bmatovu/laravel-mtn-momo)
[![Build Status](https://travis-ci.org/mtvbrianking/laravel-mtn-momo.svg?branch=master)](https://travis-ci.org/mtvbrianking/laravel-mtn-momo)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/mtvbrianking/laravel-mtn-momo/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/mtvbrianking/laravel-mtn-momo/?branch=master)
[![StyleCI](https://github.styleci.io/repos/175959117/shield?branch=master)](https://github.styleci.io/repos/175959117)

### Introduction

This package offers everything you need to integrate the [MTN MOMO API](https://momodeveloper.mtn.com) in your Laravel application. It provides a wrapper around the core MTN Momo API services, leaving you to worry about other parts of your application.

### [Installation](https://packagist.org/packages/bmatovu/laravel-mtn-momo)

To get started, install the package via the Composer package manager:

```
composer require bmatovu/laravel-mtn-momo
```

Next, for Laravel 5.3, 5.4; you need register the Passport service provider in the providers array of your `config/app.php` configuration file. For later Laravel versions, this package is auto-discoverable.

```php
'providers' => array(
    // ...
   Bmatovu\MtnMomo\MtnMomoServiceProvider::class,
),
```

**Configuration customization**

If you wish to customize the default configurations, you  may export the default configuration using

`php artisan vendor:publish --tag=mtn-momo-configuration`

### Database Migration

The package service provider registers its own database migrations with the framework, so you may migrate your database after installation. The migration will create a tokens tables your application needs to store access tokens from MTN MOMO API.

```
php artisan migrate
```

**Migration customization**

If you are not going to use the package default token migrations, you  may export the default migration using

`php artisan vendor:publish --tag=mtn-momo-migrations`

### Prerequisites

You will need the following to get started with you integration...

1. Create a [**developer account**](https://momodeveloper.mtn.com/signup) with MTN MOMO.
2. Subscribe to a [**product/service**](https://momodeveloper.mtn.com/products) that you wish to consume.

### Bootstrapping

Now you need to run the `mtn-momo:init` command. This command will create the necessary setting in you're `.env` file as you walkthrough is steps. These settings are need for authentication and communication with the MTN MOMO API.

```
php artisan mtn-momo:init
```

Add screenshot here...

The package is equipped with [more Artisan commands](#more-artisan-command-utilities) that will ease your life.

### Usage

Sample code...

### More Artisan commands

- Register client APP ID.

`php artisan mtn-momo:register-id`

- Validate client APP ID.

`php artisan mtn-momo:validate-id`

- Request client APP secret.

`php artisan mtn-momo:request-secret`
