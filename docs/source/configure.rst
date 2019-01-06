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
- ``ENABLE_DRIFT`` - Enable `Drift <https://drift.com>`_  
- ``ENABLE_CRISP`` - Enable `Crisp <https://crisp.chat>`_  
- ``ENABLE_ONESIGNAL`` - Enable `Onesignal <https://onesignal.com>`_  

Backup Settings
---------------

- ``BACKUP_DISKS`` - Comma separated list of backup disks e.g **local,s3**
- ``BACKUPS_MAIL_ALERT`` - Email to send notifications on successfull backup
- ``BACKUPS_SLACK_WEBHOOK`` - Slack webhook to post backup notifications
- ``BACKUPS_SLACK_CHANNEL`` - Slack channel to post backup notifications. Default blank

Using a (Reverse) Proxy
"""""""""""""""""""""""

If you need to set a list of trusted (reverse) proxies you can modify **app/Http/Middleware/TrustProxies.php** file.  
Your trusted proxies should be listed as an array on the **$proxies** property of this middleware. In addition to configuring the trusted proxies, you may configure the proxy **$headers** that should be trusted:

.. code-block:: shell

   protected $proxies = [
        '192.168.1.1',
        '192.168.1.2',
        '10.0.0.0/8',
        '192.168.0.0/16'
    ];
