# Resources

The package works with any resource provided by Prestashop web service, 
you can find a details of it on the <a href="https://devdocs.prestashop.com/1.7/webservice/resources/" target="_blank">prestashop documentation</a>.

```php
use Lucasgiovanny\LaravelPrestashop\Facades\Prestashop;

/*
 * Any resource will be available through the method of its name
 */

$orders    = Prestashop::orders()->get();     // Orders
$customers = Prestashop::customers()->get();  // Customers
$products  = Prestashop::products()->get();   // Products
// $resource = Prestashop::resource_name()->get();   // Any resource from web service :)
```
