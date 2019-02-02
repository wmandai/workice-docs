Install
========

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
- Iconv
- GD

Manual Install
^^^^^^^^^^^^^^

Step 1: Download the code
"""""""""""""""""""""""""

Download the code from Envato Market Downloads page.  
The zip includes all dependencies.

https://workice.com

- Release Notes: `Changelogs <changelogs.html>`__ 

- Feature requests: `desk.workice.com/features <https://desk.workice.com/features>`_

Step 2: Upload the code to your server
""""""""""""""""""""""""""""""""""""""

Copy the ZIP file to your server and then check that the storage folder has 755 permissions and is owned by the webserver user.

.. code-block:: shell

   cd /path/to/workice
   chmod -R 755 storage 
   sudo chown -R www-data:www-data storage bootstrap public

Step 3: Setup the database
""""""""""""""""""""""""""

You’ll need to create a new database along with a user to access it. Most hosting companies provide an interface to handle this or you can run the SQL statements below.

.. code-block:: shell

	CREATE DATABASE workicecrm;  
	CREATE USER 'workicecrm' IDENTIFIED BY 'workicecrm##';  
	GRANT ALL PRIVILEGES ON workicecrm.* to workicecrm@'%' identified by 'workicecrm##';  
	FLUSH PRIVILEGES;

Step 4: Configure the web server
""""""""""""""""""""""""""""""""

Once you can access the site the initial setup screen will enable you to configure the database and email settings as well as create the initial admin user.

Step 5: Configure the application
"""""""""""""""""""""""""""""""""

See the `details here <configure.html>`_ for additional configuration options.

Troubleshooting
^^^^^^^^^^^^^^^

- Check your webserver log (ie, /var/log/apache2/error.log) and the application logs (storage/logs/laravel-error.log) for more details or set ``APP_DEBUG=true`` in .env
- To resolve ``[Symfony\Component\Debug\Exception\FatalErrorException] Class 'SomeClass' not found`` try running php artisan optimize
- To resolve ``file_put_contents(...): failed to open stream: Permission denied`` run ``chmod -R 777 storage`` then ``chmod -R 755 storage``
- Running ``composer install --no-dev`` and ``composer dump-autoload`` can sometimes help with composer problems.
- Composer install error: ``Fatal error: Allowed memory size of...`` Try the following: ``php -d memory_limit=-1 /usr/local/bin/composer install --no-dev``
