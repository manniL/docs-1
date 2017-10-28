---
name: FacebookMessenger
slug: facebook-messenger
---

After installing add the following configuration to your `config/shield.php` file:

````php
'services' => [
    'facebook-messenger' => [
        'driver' => \Shield\FacebookMessenger\FacebookMessenger::class,
        'options' => [
            'app_secret' => 'your-app-secret-key'
        ]
    ]
]
````

You can now add the middleware to your routes like so:

````php
Route::middleware('shield:facebook-messenger')->post('/hooks/facebook-messenger', 'HooksController@facebookMessenger');
````
