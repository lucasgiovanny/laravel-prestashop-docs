
# Basic Usage

-   [Retrieve all from a resource](#example)
-   [Single resource](#find)
-   [Select fields](#display)
-   [Filters](#Filters)

<a name="example"></a>

## Retrieve information from a resource

Let's use the `orders` resource from Prestashop web service as an example:

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;
use Lucasgiovanny\LaravelPrestashop\Resources\Orders;
$orders = Prestashop::orders()->get();
// This will output a Laravel collection with all orders
foreach($orders as $order){
    $order->id;
    $order->total_paid;
    ///...
}
//Because every one likes it on their own ways, It's also possible to use the resource classes.
$prestashop_connection = new Prestashop();
$order = new Orders($prestashop_connection)->get();
//This will output the exact same laravel collection but then from the resource instance :D
```

<a name="find"></a>

## Return a single resource

You can use `find()` method to find a resource by id or the `first()` method to retrieve the first element from the request.

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

$orders = Prestashop::customers()->find(23);
$orders = Prestashop::customers()->first();
```

<a name="display"></a>

## Choose the data you want to display

You can use `display()` method or the `select()` method.

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

$orders = Prestashop::orders()->select('id')->get(); //It'll return only order id

$orders = Prestashop::orders()->select(['id', 'reference','invoice_number'])->get();
```

<a name="filters"></a>

## Using filters

You can use `filter()` method or the `where()` method.

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

// Works like Laravel Eloquent query builder method! :)
$orders = Prestashop::orders()->filter('reference', 'XKBKNABJK')->get();

$orders = Prestashop::orders()->where('reference','BEGIN', 'XKB')->get();
```

## Using OrderBy

You can use `orderBy()`,`orderByDesc()`,`sortBy()`, `sortByDesc`, `sort()` .
```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

// Works like Laravel Eloquent query builder method! :)
$orders = Prestashop::orders()->filter('reference', 'XKBKNABJK')->OrderBy('reference')->get();

$orders = Prestashop::orders()->where('reference','BEGIN', 'XKB')->sort('reference','ASC')->get();
```
