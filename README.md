# Larave SSE

Fork of https://github.com/tonyhhyip/laravel-sse . Made for Laravel 8.

This library provides Server Sent Event for Laravel using [libSSE-php](https://github.com/tonyhhyip/libSSE-php)


## Install - Composer
To install Laravel SSE as a Compsoer package to be used in Laravel 5, simply add this to your `composer.json`:

```json
"artel-studio/laravel-sse": "~1.0"
```

and run `composer update`.

Once it is installed, you can register the `SseServiceProvider` in `app/config/app.php` in `providers` array.
If you want, you can also add the alias SSE:

```php
'providers' => [
    ...
    Sse\Laravel\SseServiceProvider::class
],
'alias' => [
    ...
    'SSE' => Sse\Laravel\Facade\SSE::class
]
```

## Usage

You can inject the SSE in your controller
```php

class HomeController extends Controller
{
    public function sse(SSE $sse)
    {
        // Add your event listener
        return $sse->createResponse();
    }
}

```
