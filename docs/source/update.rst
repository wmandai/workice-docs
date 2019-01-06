Update
======

.. NOTE:: We recommend backing up your database with mysqldump before updating the app.

To update your CRM got to **Settings > System info** and click on **Schedule Update**.  
Enter the time when the app should update and timezone.

.. attention:: Your application will be set to maintanance mode when performing the update and restored after the update process has completed.

If you're moving servers make sure to copy over the .env file.

You can manually run the update with the following command.

.. code-block:: shell

	php artisan app:update

.. TIP:: You can see the detailed `changelogs </changelog.html>`_ for each release.

Version 2.0
"""""""""""

Copy .env.example to .env and set config settings

Check that ``/path/to/workice/storage`` has 755 permissions and is owned by the webserver user
