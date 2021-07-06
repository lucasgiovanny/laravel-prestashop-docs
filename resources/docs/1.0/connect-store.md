# Connect Store

- [Via Package Manager](#composer)
- [Publish Configuration file](#publish-configuratio)

<a name="composer"></a>
## Set store on the config file

To connect your Prestashop webservice, you can define this settings on your `.env` file:

```env
PRESTASHOP_ENDPOINT=https://prestashop.example/api
PRESTASHOP_TOKEN=YOUR-WEBSERVICE-TOKEN
```

If you prefer, you can define it directly on the `config/prestashop.php` file

<a name="composer"></a>
## On-demand

You can also define the store directly when executing an action:
```php
use LucasGiovanny\LaravelPrestashop\Facades\Prestashop;

Prestashop::store("https://prestashop.example.com/api", "YOUR-WEBSERVICE-TOKEN")
    ->orders()
    ->get();
```