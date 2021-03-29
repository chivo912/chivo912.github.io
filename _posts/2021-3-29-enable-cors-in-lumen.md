---
layout: post
title: Enable CORS in Lumen
---

Consider creating a CorsMiddleware.php file with the following code.
```php
<?php namespace App\Http\Middleware;

    use Closure;

    class CorsMiddleware
    {
     /**
     * Handle an incoming request.
     *
     * @param  \Illuminate\Http\Request  $request
     * @param  \Closure  $next
     * @return mixed
     */
    public function handle($request, Closure $next)
    {
        $headers = [
            'Access-Control-Allow-Origin'      => '*',
            'Access-Control-Allow-Methods'     => 'POST, GET, OPTIONS, PUT, DELETE',
            'Access-Control-Allow-Credentials' => 'true',
            'Access-Control-Max-Age'           => '86400',
            'Access-Control-Allow-Headers'     => 'Content-Type, Authorization, X-Requested-With'
        ];

        if ($request->isMethod('OPTIONS'))
        {
            return response()->json('{"method":"OPTIONS"}', 200, $headers);
        }

        $response = $next($request);
        foreach($headers as $key => $value)
        {
            $response->header($key, $value);
        }

        return $response;
    }
}
```
After saving it in your middleware folder, enable it by adding it to your `bootstap/app.php` file, on the list of you middleware like this
```php
$app->middleware([
    ...
    App\Http\Middleware\CorsMiddleware::class // Add this

]);
```
I hope it helps.