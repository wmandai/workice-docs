Install
==============

Thanks for purchasing `Workice CRM <https://workice.com>`__.

.. NOTE:: Workice CRM is build with `Laravel Framework <https://laravel.com>`__

.. Note:: The applications requires PHP >= 7.1.3 and MySQL.

Required PHP Extensions
^^^^^^^^^^^^^^^^^^^^^^^
- OpenSSL
- PDO
- Mbstring
- Tokenizer
- JSON
- CURL
- Mysqli
- IMAP
- Zip
- GD
  
Release Notes: `Changelogs <changelogs.html>`__ 

Any feature you need to see on Workice? `request it here <https://desk.workice.com>`_

Create Database
^^^^^^^^^^^^^^^^^
You’ll need to create a new database along with a user to access it. Most hosting companies provide an interface to handle this or you can run the SQL statements below.

 - Give your database a name e.g **workicecrm**
 - Create a database user and set up a password
 - Add the user to the database and give the user **All privileges** to the database

.. code-block:: shell

	CREATE DATABASE workicecrm;  
	CREATE USER 'workicecrm' IDENTIFIED BY 'workicecrm@@';  
	GRANT ALL PRIVILEGES ON workicecrm.* to workicecrm@'%' identified by 'workicecrm@@';  
	FLUSH PRIVILEGES;

- You will need to enter this credentials in the steps below.

File Permissions
""""""""""""""""""
The webserver should be able to write to this directories **storage**, **public** and **bootstrap/cache**.
Here is a sample of how you can set the permissions in ubuntu server.

.. code-block:: shell

   sudo chown -R ubuntu:www-data /path/to/workice
   cd /path/to/workice
   sudo find -type f -exec chmod 664 {} \;
   sudo find -type d -exec chmod 775 {} \;
   sudo chgrp -R www-data bootstrap/cache storage
   sudo chmod -R ug+rwx bootstrap/cache storage

There are 2 steps to install Workice CRM
 - Using the built in web installer
 - Artisan install method (Requires terminal)
   
Web Installer
^^^^^^^^^^^^^^^
Download the code from Envato Market Downloads page. 
The zipped file includes all dependencies.
The following steps shows how to install Workice CRM;

Shared hosting with cpanel (Sub Domain)
""""""""""""""""""""""""""""""""""""""""""""""""""""""
.. TIP:: Use this method only if you want to install Workice on a sub domain e.g crm.yourdomain.com

The steps below shows how you can install workice to be accessible via a sub domain e.g **https://crm.your domain.com**

 - Create a folder inside **public_html or www** e.g **workice** and upload your downloaded files into the folder (Make sure it includes hidden files e.g .env)
 - Go to sub domains on your cpanel dashboard and create a sub domain
 - Enter **crm** as your subdomain name e.g crm.yourdomain.com
 - Enter **public_html/workice/public** as your sub domain Document Root
 - Save it and access **http://crm.your-domain.com/installer** 
 
 .. ATTENTION:: The url **/installer** does not point to a folder so do not attempt to create a folder named installer

Shared hosting with cpanel (ROOT FOLDER)
""""""""""""""""""""""""""""""""""""""""""""""""""""""

.. TIP:: Use this method only if you want to install Workice on your main domain e.g yourdomain.com

 - Upload the files to your server in the same location where public_html or www folder is located.
 - Do not upload it inside the public_html or www folder
 - Now move the **public** folder alone to **public_html or www** folder.
 - You can now access the web installer by visiting http://your-domain.com/installer
 


Installation
""""""""""""""
Once you can access the site the initial setup screen will enable you to configure the database and email settings as well as create the initial admin user.
The first page of the web installer checks if your server meets the requirements for Workice to run.

.. ATTENTION:: Workice requires PHP 7.1.3+

Click **Next** if everything is alright if an extension is missing please contact your hosting provider or install it.
The next step checks **directory permissions**. The folders listed should be writable please do NOT set your permissions to **777**.
The next step requires database and account information.

- Enter your application name and application URL (e.g https://crm.your-domain.com)
- Enter your database access information that you used when creating database.
- Enter your admin account information. (This is the admin account you are going to login with)
- Click on install and Workice will perform the migrations and seeding.
- If everything went well, you should get a success screen. Click on **Exit** and login using admin account you created above.
  

.. ATTENTION:: You will need to setup email sending inorder to verify admin account. More on that in next article.


Artisan Installer
^^^^^^^^^^^^^^^^^^^^
If you need to install Workice CRM using ``php artisan`` command proceed as follows;
 - Open **.env** file and update your database credentials i.e **DB host,DB User etc** (You can change other configurations later).
 - Run command ``php artisan workice:install`` to start the installation.
 - You will be asked to enter admin email and password.
 - After successfull install you can now access your dashboard using http://crm.your-domain.com
 - Use your admin account to login.
  
.. NOTE:: Admin account created using ``php artisan workice:install`` command does not require email verification.

Email Configuration
^^^^^^^^^^^^^^^^^^^^^

 - Workice CRM supports SMTP, Mailgun, Postmark, SparkPost, Amazon SES, and sendmail.
 - If you have no idea how to configure email sending, read on the next guide **Configuration**.

CRON Configuration
^^^^^^^^^^^^^^^^^^^^
Add a CRON job as shown below;

``* * * * * cd /path-to-workice && php artisan schedule:run >> /dev/null 2>&1``

This Cron will call Workice command scheduler every minute. When the **schedule:run** command is executed, Workice will evaluate your scheduled tasks and runs the tasks that are due.

Queue Configuration
^^^^^^^^^^^^^^^^^^^^^^
Workice CRM relies heavily on ``queue workers``. 

.. NOTE:: For VPS or AWS EC2 users, we recommend installing Supervisord to monitor your processes. Steps on how to install Supervisor on ubuntu are described below

To run queue workers use this command;

``php artisan queue:work --queue=default,high,normal,low --tries=3``

Queues on Shared Hosting
""""""""""""""""""""""""""
To run queues on shared hosting;
 - Open **app/Console/Kernel.php** and uncomment the line ``$schedule->command('queue:work --workicedaemon --queue=default,high,normal,low --tries=3')....``
 - Now setup your CRON ``* * * * * php /path/to/workice/artisan schedule:run >/dev/null``
 - We have modified the queue command to only run jobs and exit to avoid server memory issues.


Installing Supervisor
"""""""""""""""""""""""
Supervisor is a process monitor for the Linux operating system, and will automatically restart your queue:work process if it fails. To install Supervisor on Ubuntu, you may use the following command:

``sudo apt-get install supervisor``

Supervisor configuration files are typically stored in the **/etc/supervisor/conf.d** directory. Within this directory, you may create any number of configuration files that instruct supervisor how your processes should be monitored. For example, let's create a workice-worker.conf file that starts and monitors a queue:work process:

.. code-block:: shell

	[program:workice-worker]
	process_name=%(program_name)s_%(process_num)02d
	command=php /path/to/workice/artisan queue:work --queue=default,high,normal,low --tries=3
	autostart=true
	autorestart=true
	user=ubuntu
	numprocs=1
	redirect_stderr=true
	stdout_logfile=/path/to/workice/worker.log

You can refer to `laravel docs <https://laravel.com/docs/5.7/queues#supervisor-configuration>`__ 

Starting Supervisor
""""""""""""""""""""""
Once the configuration file has been created, you may update the Supervisor configuration and start the processes using the following commands:

``sudo supervisorctl reread``

``sudo supervisorctl update``

``sudo supervisorctl restart all``

For more information on Supervisor, consult the Supervisor documentation.


See the `details here <configure.html>`_ for additional configuration options.


Troubleshooting
^^^^^^^^^^^^^^^^^

- Check your webserver log (ie, /var/log/apache2/error.log) and the application logs (storage/logs/laravel-error.log) for more details or set ``APP_DEBUG=true`` in .env
- Getting 404 not found when i access http://crm.mydomain.com/installer - Ensure your sub domain ROOT Document points to /path/to/workice/public folder and not /path/to/workice folder.
- I cannot see a folder named **installer** - The url /installer is a laravel route and not a folder. You will be redirected to /installer if the application detects that the app needs to be installed.
- To resolve ``file_put_contents(...): failed to open stream: Permission denied`` run ``chmod -R 777 storage`` then ``chmod -R 755 storage``
- Running ``composer install --no-dev`` and ``composer dump-autoload`` can sometimes help with composer problems.
- Composer install error: ``Fatal error: Allowed memory size of...`` Try the following: ``php -d memory_limit=-1 /usr/local/bin/composer install --no-dev``
- If you are installing on PHP 7.3 and encounter an error ``preg_match_all(): JIT compilation failed: no more memory`` you will need to modify your php.ini file and enter **pcre.jit=0** to fix the issue.
- My images are not loading - May be caused by wrong symlink. Edit public/index.php file and write this line at the top of the code after ``<?php`` opening tag ``symlink('../your-crm-folder/storage/app/public', './storage');``
- My CRONs are not running and i get an error ``'ErrorException' with message 'Invalid argument supplied for foreach()' in /home/project/vendor/symfony/console/Input/ArgvInput.php`` to fix this, enter your CRON to run every minute as shown ``php -d register_argc_argv=On /path/to/workice/artisan schedule:run >/dev/null``
