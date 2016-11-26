# middleware

FastD Middleware

## requirement

* php >= 5.6

## installation

```
composer require "fastd/middlware:1.0.x-dev" -vvv
```

```php
$middleware = new Middleware(function (RequestInterface $request, DelegateInterface $next) {
    // delegate control to next middleware
    return $next($request);
});

$middleware2 = new Middleware(function (RequestInterface $request, DelegateInterface $next) {
    echo 'world';
});

$stack = new Stack();
$stack->withoutMiddleware($middleware);
$stack->withoutMiddleware($middleware2);

$response = $stack->process(new ServerRequest());
```

## License MIT
