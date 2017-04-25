# HTTP Message Strategies

This document describes extensible interfaces for common strategies to process
HTTP Messages defined by [PSR-7](http://www.php-fig.org/psr/psr-7/).

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

The final implementations MAY decorate the objects and methods with more
functionality than the one proposed but they MUST implement the indicated
interfaces/functionality.

### References

- [PSR-7](http://www.php-fig.org/psr/psr-7/)
- [RFC 2119](http://tools.ietf.org/html/rfc2119)

## 1. Specification

* An _HTTP Message Strategy_ is a component which can be used to process HTTP messages.
This specification defines contracts for the most common strategies, which accept a _PSR-7 Message_ and produce a _PSR-7 Message_.
* An _Operator_ is a functional component which returns a result of the same type as its operand.
* A _Action_ is a functional component which accepts a request and returns a `Psr\Http\Message\ResponseInterface` result.

## 2. Package

The interfaces described are provided as part of the [psr/http-message-strategies](https://github.com/http-message-strategies-interop/http-message-strategies) package.

## 3. Interfaces

An _HTTP Message Strategy_ using this standard MUST implement the corresponding `interface` and the behaviour described by its comments.

### 3.1 `Psr\Http\Message\Strategies\RequestOperatorInterface`

```php
namespace Psr\Http\Message\Strategies;

use Psr\Http\Message\RequestInterface;

/**
 * Defines a contract for functions which accept a request argument and produce a request.
 */
interface RequestOperatorInterface
{
    /**
     * Process a request and return the produced request.
     *
     * @param RequestInterface $request
     *
     * @return RequestInterface
     */
    public function __invoke(RequestInterface $request);
}
```

### 3.2 `Psr\Http\Message\Strategies\ActionInterface`

```php
namespace Psr\Http\Message\Strategies;

use Psr\Http\Message\RequestInterface;
use Psr\Http\Message\ResponseInterface;

/**
 * Defines a contract for functions which accept a request argument and produce a response.
 */
interface ActionInterface
{
    /**
     * Process a request and return the produced response.
     *
     * @param RequestInterface $request
     *
     * @return ResponseInterface
     */
    public function __invoke(RequestInterface $request);
}
```

### 3.3 `Psr\Http\Message\Strategies\ResponseOperatorInterface`

```php
namespace Psr\Http\Message\Strategies;

use Psr\Http\Message\ResponseInterface;

/**
 * Defines a contract for functions which accept a respose argument and produce a respose.
 */
interface ResponseOperatorInterface
{
    /**
     * Process a respose and return the produced respose.
     *
     * @param ResponseInterface $respose
     *
     * @return ResponseInterface
     */
    public function __invoke(ResponseInterface $respose);
}
```

### 3.4 `Psr\Http\Message\Strategies\ServerActionInterface`

```php
namespace Psr\Http\Message\Strategies;

use Psr\Http\Message\ResponseInterface;
use Psr\Http\Message\ServerRequestInterface;

/**
 * Defines a contract for functions which accept a server request argument and produce a respose.
 */
interface ServerActionInterface
{
    /**
     * Process a server request and return the produced response.
     *
     * @param ServerRequestInterface $request
     *
     * @return ResponseInterface
     */
    public function __invoke(ServerRequestInterface $request);
}
```

### 3.5 `Psr\Http\Message\Strategies\ServerRequestOperatorInterface`

```php
namespace Psr\Http\Message\Strategies;

use Psr\Http\Message\ServerRequestInterface;

/**
 * Defines a contract for functions which accept a server request argument and produce a server request.
 */
interface ServerRequestOperatorInterface
{
    /**
     * Process a request and return the produced server request.
     *
     * @param ServerRequestInterface $request
     *
     * @return ServerRequestInterface
     */
    public function __invoke(ServerRequestInterface $request);
}
```
