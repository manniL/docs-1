---
name: Braintree
slug: braintree
---

After installing add the following configuration to your `config/shield.php` file:

````php
'services' => [
    'braintree' => [
        'driver' => \Shield\Braintree\Braintree::class,
        'options' => [
            'environment' => env('BRAINTREE_ENVIRONMENT', 'development'),
            'merchant_id' => env('BRAINTREE_MERCHANT_ID', 'your-merchant-id'),
            'public_key' => env('BRAINTREE_PUBLIC_KEY', 'your-public-key'),
            'private_key' => env('BRAINTREE_PRIVATE_KEY', 'your-private-key'),
        ]
    ]
]
````

You can now add the middleware to your routes like so:

````php
Route::middleware('shield:braintree')->post('/hooks/braintree', 'HooksController@braintree');
````
