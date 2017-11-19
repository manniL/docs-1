---
name: Shopify
slug: shopify
---

After installing add the following configuration to your `config/shield.php` file:

````php
'services' => [
    'shopify' => [
        'options' => [
            'token' => 'your-webhook-token',
        ]
    ]
]
````

You can now add the middleware to your routes like so:

````php
Route::middleware('shield:shopify')->post('/hooks/shopify', 'HooksController@shpoify');
````
