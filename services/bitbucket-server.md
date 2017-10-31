---
name: Bit Bucket Server
slug: bitbucket-server
---

After installing add the following configuration to your `config/shield.php` file:

````php
'services' => [
    'bitbucketserver' => [
        'driver' => \Shield\BitBucketServer\BitBucketServer::class,
        'options' => [
            'token' => 'your-webhook-token'
        ]
    ]
]
````

You can now add the middleware to your routes like so:

````php
Route::middleware('shield:bitbucketserver')->post('/hooks/bitbucketserver', 'HooksController@bitbucketserver');
````
