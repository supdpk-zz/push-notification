# PushNotification
The Laravel 5 Package for Push Notification. Currently supported Services: <a href="https://firebase.google.com/">Firebase Cloud Messaging</a>

<h2>Installation</h2>
<b>Step 1:</b> Install package using composer
<pre><code>
    composer require belbase/push-notification
</pre></code>

<b>Step 2:</b> Add the service provider to the config/app.php file in Laravel (Optional for Laravel 5.5)
<pre><code>
    Belbase\PushNotification\Providers\IndipayServiceProvider::class,
</pre></code>

<b>Step 3:</b> Add an alias for the Facade to the config/app.php file in Laravel (Optional for Laravel 5.5)
<pre><code>
    'PushNotification' => Belbase\PushNotification\Facades\PushNotification::class,
</pre></code>

<b>Step 4:</b> Publish the config & Middleware by running in your terminal
<pre><code>
    php artisan vendor:publish
</pre></code>

<h2>Usage</h2>

Edit the config/indipay.php. Set the appropriate Gateway and its parameters. Then in your code... <br>
<pre><code> use Belbase\PushNotification\Facades\PushNotification;  </code></pre>
Initiate Purchase Request and Redirect using the default service:-
```php 
      /* All Required Parameters by your Gateway */
      
      $metaData=[
        // enter data to send along with notification
      ];
      return PushNotification::to('_tokenID')->setMessage('title','body',$metaData)->sendMessage();
```