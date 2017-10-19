---
name: Mailgun
slug: mailgun
---

After installing add the following configuration to your `config/shield.php` file:

````php
'services' => [
    'mailgun' => [
        'driver' => \Shield\Mailgun\Mailgun::class,
        'options' => [
            'token' => env('MAILGUN_SECRET', 'your-custom-mailgun-secret'),
            'tolerance' => 300, // seconds (5 minutes)
        ],
    ],
]
````

You can now add the middleware to your routes like so:

````php
Route::middleware('shield:mailgun')->post('/hooks/mailgun', 'HooksController@mailgun');
````