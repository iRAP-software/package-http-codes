Awesome HTTP Codes Package
==========================

To use this package of defines you need to manually include the

## Usage

Download this package into your project with the command:
```
composer require irap/http-codes
```


Below is an example of using the package to return a 404 JSON response for an API request.

```php
<?php
http_response_code(iRAP/Http/HttpCode::NOT_FOUND);

$body = array(
    "result" => "error",
    "message" => "Resource not found.",
);

header('Content-Type: application/json');
die(json_encode($body));
```


Alternatively...

```php
<?php
use iRAP\Http\HttpCode;

http_response_code(HttpCode::NOT_FOUND);

$body = array(
    "result" => "error",
    "message" => "Resource not found.",
);

header('Content-Type: application/json');
die(json_encode($body));
```

There's also a method to check if a passed parameter is a valid http status code based on this.
```php
<?php
use iRAP\Http\HttpCode;

if (HttpCode::isValid(404)) {
    echo "Valid HTTP status code";
} else {
    echo "Invalid HTTP status code";
}
```
