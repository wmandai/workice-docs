Update
======

.. NOTE:: We recommend backing up your database with mysqldump before updating the app.

Workice CRM checks for updates daily and notifies you via email if there is a new update. You can disable update notifications in **Settings** > **System Settings** > **Update Notifications**.

.. ATTENTION:: Updates require a valid purchase code. Enter your purchase code in **Settings** > **System Settings** and save.

To update your CRM got to **Settings > System info** and click on **Schedule Update**.  
Enter the time when the app should update and timezone.

.. ATTENTION:: Your application will be set to maintenance mode when performing the update and restored after the update process has completed.

If you're moving servers make sure to copy over the .env file.

.. TIP:: You can see the detailed `changelogs </changelog.html>`_ for each release.

Version 2.0
"""""""""""

Copy .env.example to .env and set config settings

Check that ``/path/to/workice/storage`` has 755 permissions and is owned by the webserver user
