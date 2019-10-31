# [Routing](http://pfinal.cn)

## 安装

环境要求：PHP >= 5.4、7+

* 使用 [composer](https://getcomposer.org/)

```shell
composer require pfinal/routing
```

使用示例 

```php
require __DIR__ . '/vendor/autoload.php';

use Symfony\Component\HttpFoundation\Request;
use PFinal\Routing\Router;

$router = new Router();

$router->get('/', function () {
    return 'index';
});

$router->any('/blog/:id', function ($id) {
    return $id;
});

$router->post('/blog/:name/update', function ($name) {
    return $name;
});

$request = Request::createFromGlobals();

$response = $router->dispatch($request);
$response->send();
```