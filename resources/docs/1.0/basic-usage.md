# Basic Usage

- [Retrieve all from a resource](#retrieve-all)
- [Create a resource](#create-resource)
- [Update a resource](#update-resource)
- [Delete a resource](#delete-resource)

<a name="retrieve-all"></a>
## Retrieve all from a resource

Let's use the `orders` resource from Prestashop webservice as an example:

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

$orders = Prestashop::orders()->get();
// This will output a Laravel collection with all orders

foreach($orders as $order){
    $order->id;
    $order->total_paid;
    ///...
}
```

<a name="create-resource"></a>
## Create a resource

Let's use the `orders` resource from Prestashop webservice as an example:

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;
use Lucasgiovanny\LaravelPrestashop\Models\Resource as PrestashopResource;

// Using 'create' method
$order = Prestashop::orders()->create([
    'reference' => "Order nº 1",
    'total'     => 20.00,
]);

// Using Resource class
$order = new PrestashopResource("orders");
$order->reference = "Order nº 2";
$order->total     = 20.00;
$order->save();
```

<a name="update-resource"></a>
## Create a resource

Let's use the `orders` resource from Prestashop webservice as an example:

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;
use Lucasgiovanny\LaravelPrestashop\Models\Resource as PrestashopResource;

$order = Prestashop::orders()->find(1);

// Set class properties
$order->reference = "Order nº 2";
$order->total     = 20.00;
$order->save();

// Use update method
$order->update([
    'reference' => "Order nº 1",
    'total'     => 20.00,
]);
```

<a name="delete-resource"></a>
## Delete a resource

Let's use the `orders` resource from Prestashop webservice as an example:

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

$order = Prestashop::orders()->find(1);
$order->delete();
```