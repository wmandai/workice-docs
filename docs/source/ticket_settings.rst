Ticket Settings
================
You can view and edit ticket configuration in your CRM by going to **Settings** and clicking on the **Ticket Settings**.

You can modify the settings below;

 - **Ticket Prefix**: The default ticket prefix e.g TKT
 - **Ticket Number Format**: Ticket code format e.g -[yyyy][mm][dd]-[i] (yyyy represents the Year, mm for month, dd for day).
 - **Ticket Start Number**: Ticket code numbers will start from the value entered here.
 - **Default Department**: When a department is not specified when creating a ticket, this department will be used.
 - **Auto Close Ticket**: Closes tickets that have not been active for X days
 - **Ticket Due Days**: The default number of days a ticket should take before it's closed. Default 3 days
 - **Feedback Request**: Ask for closed ticket review after X days. Enter 0 to disable
 - **Enable Answer Bot**: Auto search the knowledgebase and attempt to find articles that match what the customer is looking for. Answerbot will send an email with a link to ticket related articles.

IMAP Settings
^^^^^^^^^^^^^^^
Integrate with your existing email infrastructure to receive tickets via email.
For those customers that prefer to use email, Workice provides powerful email integration functionality that can intelligently read incoming emails and generate new help desk tickets as well as add comments to existing open tickets.

 - **IMAP**: Enable ticket email retrival via IMAP
 - **IMAP Host**: Your IMAP Host e.g imap.gmail.com
 - **IMAP Username**: Your IMAP username/full address
 - **IMAP Password**: Imap Password
 - **Mail Port**: IMAP port e.g 587
 - **Mail Flags**: IMAP flags. Default /imap/ssl/novalidate-cert
 - **Mailbox**: Mail folder. Default INBOX
