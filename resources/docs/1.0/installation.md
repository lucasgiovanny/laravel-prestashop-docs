# Installation

- [Via Package Manager](#composer)
- [Publish Configuration file](#publish-configuratio)

<a name="composer"></a>
## Via package manager

You can install the package via composer:

```bash
composer require lucasgiovanny/laravel-prestashop
```
<a name="publish-configuration"></a>
## Publishing configuration file

After installation, you can publish the config file:
```bash
php artisan vendor:publish --provider="Lucasgiovanny\LaravelPrestashop\LaravelPrestashopServiceProvider" --tag="laravel-prestashop-config"
```