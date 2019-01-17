Email Templates
=====================

You can modify email templates for invoice emails, estimates, projects etc. To do so, select **Settings** from the main menu sidebar then click **Translations**. 

Click on **Emails** button at the top bar to open email translations.

Select the language you want to modify;

.. ATTENTION:: The english version variables are named in {module}.{action}.{type} format (dot notation). Example; if you need to edit the message that will be sent when you send an invoice, look for a variable named ``invoices.sending.body``. To edit sent message subject, modify ``invoices.sending.subject`` value. 

Example
^^^^^^^^^^^^^^^^^^^^
Let's say we want to modify the German message that should be sent to us when we receive a payment.

Go to Settings and click on Translations;
 - Click **Emails** button.
 - Look for German Language and click the **Pencil** icon to modify text
 - Look for English translation ``payments.received.body``. 
 - The English version displayed is ``You have received payment of :amount on :date for invoice :code``
 - Change the text that appears at the right side (text box) by replacing it with your German version.
 - Next time you receive a payment notification message in German, your custom message will be displayed in the email body.
 - Click **Save** button to save the changes
   
.. NOTE:: You can modify other email templates in different locales using the same procedure above.