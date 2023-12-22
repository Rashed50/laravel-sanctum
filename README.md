# laravel-Sanctum

What is Laravel Sanctum ? Laravel Sanctum provides a featherweight authentication system for SPAs (single page applications), mobile applications, and simple, token based APIs. Sanctum allows each user of your application to generate multiple API tokens for their account. These tokens may be granted abilities / scopes which specify which actions the tokens are allowed to perform..

You have to just follow a few steps to get following web services
Login API
Details API

# Getting Started

## Step 1: setup database in .env file

'''
DB_DATABASE=sacdb 
DB_USERNAME=root  
DB_PASSWORD= rashed@123
'''
 
## Step 2:Install Laravel Sanctum.
'''
composer require laravel/sanctum
'''

# Step 3:Publish the Sanctum configuration and migration files
'''
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
'''

# Step 4:Run your database migrations.
'''
php artisan migrate
'''

# Step 5:Add the Sanctum's middleware.

'''
../app/Http/Kernel.php

use Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful;

    protected $middlewareGroups = [
        ...

        'api' => [
            EnsureFrontendRequestsAreStateful::class,
            'throttle:60,1',
            \Illuminate\Routing\Middleware\SubstituteBindings::class,
        ],
    ];
],
'''





