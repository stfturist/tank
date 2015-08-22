# tank

[![Build Status](https://travis-ci.org/frozzare/wp-tank.svg?branch=master)](https://travis-ci.org/frozzare/wp-tank)  [![codecov.io](http://codecov.io/github/frozzare/wp-tank/coverage.svg?branch=master)](http://codecov.io/github/frozzare/wp-tank?branch=master)
[![License](https://img.shields.io/packagist/l/frozzare/tank.svg)](https://packagist.org/packages/frozzare/tank)

> Requires PHP 5.4

WordPress Container.

## Install

```
$ composer require frozzare/tank
```

## Example

```php
use Frozzare\Tank\Container;
use Frozzare\Tank\Service_Provider;

class Plugin_Loader extends Container {

  public function __construct() {
    $this->bind( 'number', 12345 );
  }

}

$loader = new Plugin_Loader;
echo $loader->make( 'number' );
// 12345

class Example_Provider extends Service_Provider {

  public function register() {
    $this->container->bind( 'say', 'Hello!' );
  }

}

$provider = new Example_Provider( $loader );
echo $loader->make( 'say' );
// Hello!
```

Check the [source code](https://github.com/frozzare/tank/blob/master/src/Container.php) for methods that can be used.

## License

MIT © [Fredrik Forsmo](https://github.com/frozzare)
