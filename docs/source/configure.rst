Configure
=========

You can check .env.example file to see additional settings.

CRON Setup
"""""""""""

Create one CRON that runs **every minute** as follows;

.. code-block:: shell

   * * * * * php /path-to-your-project/artisan schedule:run >/dev/null

Email Queues
""""""""""""
Queues allow you to defer the processing of a time consuming task, such as sending an email, until a later time. Deferring these time consuming tasks drastically speeds up web requests to your application.
You can change the queue driver in your .env file ``QUEUE_DRIVER=database``

.. Note:: You can process the jobs by running ``php artisan queue:work --queue=default,high,normal,low --tries=3 --daemon``.

Supervisord Configuration
-----------------------------
We highly recommend configuring supervisord to monitor your processes and restart your queue if it fails.  
Read more on `Supervisord Configuration <https://laravel.com/docs/5.7/queues#supervisor-configuration>`__


Application Configuration
"""""""""""""""""""""""""
You can set your application to production by modifying this value in .env file.

- ``APP_ENV`` - Set it to **production**
- ``APP_DEBUG`` - Set it to **false**

System Configuration
""""""""""""""""""""

Here some of the system configurations you can change in your .env  

- ``EMAIL_TRACKING_ENABLE`` - Enables email tracking for leads.  
- ``PDF_FONT`` - Font to use on PDF generated.  
- ``DAILY_DIGEST_ENABLED`` - Enables daily email summary - Default true.  
- ``DAILY_DIGEST_AT`` - Sets the time when daily summary should be sent - Default 23:58  
- ``ACTIVITY_DAYS`` - The number of days activity logs take to be cleared - Default 7 days  
- ``TICKETS_DUE_DAYS`` - Number of days before a ticket expires - Default 3 days  
- ``TASKS_DUE_DAYS`` - Days before a task is overdue - Default 7 days  
- ``ALERT_TODO_DAYS`` - Number of days to notify me before a todo is overdue  
- ``ESTIMATE_REMIND_DAYS`` - Number of days before a reminder is sent to client about expiring estimate. Default 2 days  
- ``CONTRACT_REMIND_DAYS`` - Days before a client is notified of expiring contract that has not been signed. Default 2 days  
- ``ENABLE_DRIFT`` - Enable `Drift <https://drift.com>`_  (Read below on how to configure)
- ``ENABLE_CRISP`` - Enable `Crisp <https://crisp.chat>`_  (Read below on how to configure)
- ``ENABLE_ONESIGNAL`` - Enable `Onesignal <https://onesignal.com>`_ (Read below on how to configure)
- ``ENABLE_TAWK`` - Enable `Tawk <https://tawk.to>`_   (Read below on how to configure)

Backup Settings
---------------

- ``BACKUP_DISKS`` - Comma separated list of backup disks e.g **local,s3**
- ``BACKUPS_MAIL_ALERT`` - Email to send notifications on successfull backup
- ``BACKUPS_SLACK_WEBHOOK`` - Slack webhook to post backup notifications
- ``BACKUPS_SLACK_CHANNEL`` - Slack channel to post backup notifications. Default blank
 
Email Settings
---------------
 - ``MAIL_DRIVER`` - Email driver. Default **smtp**
 - ``MAIL_HOST`` - Email host e.g **smtp.mailtrap.io**
 - ``MAIL_PORT`` - Outgoing email port e.g **2525** or **465**
 - ``MAIL_USERNAME`` - Outgoing email username
 - ``MAIL_PASSWORD`` - Outgoing email password
 - ``MAIL_ENCRYPTION`` - Default null other options **tls** and **ssl**

 - ``MAIL_FROM_ADDRESS`` - The email address that sends emails (Your company address)
 - ``MAIL_FROM_NAME`` - Your company name that appears on emails

.. ATTENTION:: To send a test email go to **Settings** -> **System Info** and click on **Test Email** button.

Paypal Configuration
---------------------
To setup paypal IPN;
 - Login to `Paypal <https://paypal.com>`__ account
 - Set the IPN to https://{YOUR-DOMAIN}/webhook/paypal/ipn replace {YOUR-DOMAIN} with your actual domain e.g https://app.workice.com/webhook/paypal/ipn

 .. ATTENTION:: To enable PayPal Live, go to **Settings** -> **Payment Settings**

Stripe Configuration
---------------------
To configure `Stripe <https://dashboard.stripe.com>`__, proceed as follows;

 - Login to your stripe dashboard account
 - Get your API Keys by clicking Developers section
 - Obtain your stripe webhook keys by clicking on Webhooks under Developers section of your stripe dashboard.

Open your .env file in Workice CRM and modify the values below;

.. code-block:: shell

	STRIPE_KEY={YOUR_STRIPE_PUBLISHABLE_KEY}
	STRIPE_SECRET={YOUR_STRIPE_SECRET_KEY}
	STRIPE_WEBHOOK_SECRET={YOUR_STRIPE_WEBHOOK_KEY}

Stripe Webhook Configuration
-----------------------------
To handle `Stripe <https://dashboard.stripe.com>`__ webhooks, proceed as follows;
 - Login to your stripe dashboard and click on Developers section.
 - Click Webhooks -> Add Endpoint button
 - Enter webhook URL as https://{YOUR-DOMAIN}/stripe/webhook replace {YOUR-DOMAIN} with your actual domain e.g https://app.workice.com/stripe/webhook

By default, Workice CRM will automatically handle cancelling subscriptions that have too many failed charges (as defined by your Stripe settings), customer updates, customer deletions, subscription updates, and credit card changes; 

Razorpay Configuration
------------------------
To configure `RazorPay <https://dashboard.razorpay.com>`__, proceed as follows;

 - Login to your razorpay dashboard account
 - Get your API Keys by clicking Settings -> API Keys section

Open your .env file in Workice CRM and modify the values below;

.. code-block:: shell

	RAZORPAY_KEY={RAZORPAY_KEYID}
	RAZORPAY_SECRET={RAZORPAY_SECRET}

.. ATTENTION:: Create Razorpay webhook and enter webhook URL as https://{YOUR-DOMAIN}/webhook/razorpay/ipn replace {YOUR-DOMAIN} with your actual domain e.g https://app.workice.com/webhook/razorpay/ipn

Braintree Configuration
------------------------
To configure `Braintree <https://www.braintreegateway.com>`__, proceed as follows;

 - Login to your braintree dashboard account
 - Get your API Keys by clicking Settings -> API section
 - Just below the API keys you'll see your Merchant ID

Open your .env file in Workice CRM and modify the values below;

.. code-block:: shell

	BRAINTREE_MERCHANT_ID={BRAINTREE_MERCHANT_ID}
	BRAINTREE_PUBLIC_KEY={BRAINTREE_PUBLIC_KEY}
	BRAINTREE_PRIVATE_KEY={BRAINTREE_PRIVATE_KEY}

.. ATTENTION:: You will need to enter your Merchant Account in Settings -> Payment Settings -> Braintree Merchant Account

.. ATTENTION:: To enable Braintree Live, go to **Settings** -> **Payment Settings**

WePay Configuration
---------------------
To configure `WePay <https://www.wepay.com>`__ gateway, proceed as follows;

 - Login to your WePay dashboard account
 - Get your API Keys by clicking on your business account
 - Copy and replace the values below with your WePay API Keys

Open your .env file in Workice CRM and modify the values below;

.. code-block:: shell

	WEPAY_ACCOUNT_ID={WEPAY_ACCOUNT_ID}
	WEPAY_CLIENT_ID={WEPAY_CLIENT_ID}
	WEPAY_SECRET_ID={WEPAY_CLIENT_SECRET}
	WEPAY_ACCESS_TOKEN={WEPAY_ACCESS_TOKEN}

.. ATTENTION:: To enable WePay Live, go to **Settings** -> **Payment Settings**

2Checkout Configuration
-------------------------
To configure `2checkout <https://2checkout.com>`__, proceed as follows;

 - Login to your `2checkout <https://2checkout.com>`__ dashboard account
 - Get your API Keys by clicking on API section
 - Obtain your SELLER ID by clicking on your 2chekout avatar and copy **Account Number**.

Open your .env file in Workice CRM and modify the values below;

.. code-block:: shell

	2CHECKOUT_PUBLISHABLE_KEY={2CHECKOUT_PUBLISHABLE_KEY}
	2CHECKOUT_PRIVATE_KEY={2CHEKOUT_PRIVATE_KEY}
	2CHECKOUT_SELLER_ID={2CHEKOUT_SELLER_ID}

.. ATTENTION:: To enable 2Checkout Live, go to **Settings** -> **Payment Settings**

Mollie Configuration
-------------------------
To configure mollie, proceed as follows;

 - Login to your `Mollie <https://www.mollie.com/dashboard>`__ dashboard account
 - Get your API Keys by clicking on Developers section

Open your .env file in Workice CRM and modify the values below;

.. code-block:: shell

	MOLLIE_KEY={MOLLIE_API_KEY}


Google Calendar Setup
"""""""""""""""""""""""
To display events from your Google Calendar, Go to **Settings** -> **System Settings** and enter your Google Calendar API key and your Google Calendar ID. Once the settings are configured, your events will display on Workice calendar.

Crisp, Drift, Onesignal and Tawk.to
""""""""""""""""""""""""""""""""""""""""""""""""
After you have signed up to the services above, proceed as follows;  

Onesignal
------------
After you have enabled onesignal in your .env, copy the **script code** they have given you and paste it in **/resources/views/partial/onesignal.blade.php** (Replace the sample code in that file).

Drift
------------
After you have enabled drift in your .env, copy the **script code** they have given you and paste it in **/resources/views/partial/drift.blade.php** (Replace the sample code in that file).

Crisp
------------
After you have enabled crisp in your .env, copy the **script code** they have given you and paste it in **/resources/views/partial/crisp.blade.php** (Replace the sample code in that file).

Tawk
------------
After you have enabled tawk.to in your .env, copy the **script code** they have given you and paste it in **/resources/views/partial/tawk.blade.php** (Replace the sample code in that file).

Google ReCaptcha
"""""""""""""""""""
To enable recaptcha, first get your recaptcha key and secret from `Google <https://www.google.com/recaptcha>`__.
Open **.env** file on the ROOT folder and enter your values as shown.

.. code-block:: shell

	NOCAPTCHA_SECRET=YOUR-RECAPTCHA-SECRET
	NOCAPTCHA_SITEKEY=YOUR-RECAPTCHA-SITE-KEY

Go to **Settings** > **System Settings** then enable **Use Recaptcha**.


Using a (Reverse) Proxy
""""""""""""""""""""""""

If you need to set a list of trusted (reverse) proxies you can modify **app/Http/Middleware/TrustProxies.php** file.  
Your trusted proxies should be listed as an array on the **$proxies** property of this middleware. In addition to configuring the trusted proxies, you may configure the proxy **$headers** that should be trusted:

.. code-block:: shell

   protected $proxies = [
        '192.168.1.1',
        '192.168.1.2',
        '10.0.0.0/8',
        '192.168.0.0/16'
    ];
