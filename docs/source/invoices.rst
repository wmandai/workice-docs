Invoices
========
.. meta::
   :description: Invoice and Project Management for freelancers and small business. Easily create and track invoices and get paid online. Manage your deals and leads.
   :keywords: projects,invoices,freelancer,deals,leads,crm,estimates,tickets,subscriptions,tasks,contacts,contracts,creditnotes,freelancer office,codecanyon

Invoices allow you to bill a Client for your products and/or services, and help you keep track of your income in Workice CRM. 
Every invoice paid means more revenue coming into your business. Create and send professional invoices to your customers in seconds. Once you’ve entered the client and tax information, you’ll have a range of actions at your fingertips – from saving a draft, to sending the invoice to the client via email, to printing a PDF hard copy.

Overview
""""""""""

The life of an invoice in Workice system is made up of a number of stages:

- **Draft/Hidden**: When you’ve created an invoice, but have not yet sent it.
- **Sent**: You’ve sent the invoice, but the client has not yet paid.
- **Viewed**: The client has opened the invoice email and viewed the invoice.
- **Partial**: The invoice has been partially paid.
- **Paid**: Congratulations! The client has paid the full invoice amount.
- **Not Paid**: The invoice remains unpaid.
- **Overdue**: The invoice has passed its due date.

Invoices list
"""""""""""""
On the invoices list page you'll see a table with the columns below;

- **Invoice #**: The number of the invoice
- **Client Name**: The name of the client
- **Status**: The current status of the invoice (Draft, Sent,  Viewed, Partial, Paid, Not Paid, Overdue)
- **Due Date**: The date the payment is due
- **Amount**: The total amount of the invoice
- **Balance**: The amount owed by the client (after credits and other adjustments are calculated)


Create Invoice
"""""""""""""""

To create a new invoice, go to the Invoices tab on the main sidebar, and click on the + Create button. This will open the Invoices / Create page offering a series of text and numerical inputs.

Note that each new invoice you create will be automatically numbered in chronological order. This will ensure your records are kept logical and organized. (You have the option to change the invoice number manually in **Settings** - **Invoice Settings**).

The form contains:

- **Ref No**: Auto assigned invoice number
- **Title**: Invoice Title e.g Acme Website Design (optional)
- **Client**: Click on the arrow at the right end of the Client field. Select the relevant client from the client list. 
- **Tax 1**: Tax 1 amount in percentage.
- **Tax 2**: Tax 2 amount in percentage.
- **Discount**: Discount as percentage or monetary amount.
- **Late Fee**: The percentage or amount to be applied if the invoice is not paid on time.
- **Extra Fee**: If there is any additional fee for the invoice add it as amount or percentage.
- **Currency**: Invoice currency. If you select ``Client Default Currency``, the selected client's currency will be used.
- **Tags**: Enter multiple tags for the invoices e.g website,logos etc (Optional)
- **Payment methods**: Select the payment methods you want your client to pay with. All enabled payment methods will be presented to the client as options so he/she can choose the payment method to use.

.. TIP:: You can create a new client while creating a new invoice. Simply click on the Create new client link, situated on the top left side of the Create page. A pop-up modal will open, enabling you to complete the new client’s details. Then continue creating the invoice for this new client.

.. ATTENTION:: If you use Braintree, you'll need to enter your Merchant Account.

- **Partial Payment Terms**: If you want to enabled partial payments, enter the phases that the invoice should be paid with their due dates. Example, 50% - Due 01-01-2019 and 50% - Due 02-02-2019. If you require an invoice to be paid once, enter 100% in the amount and the deadline/due date.

- **Notes**: Want to enter information to appear as a footer on the invoice? Enter it here. The text will appear at the bottom of the invoice.

Once you've completed creating your invoice, click on **Save** Button and you'll be redirected to the invoice page where you can enter your products/services to bill your clients.

- **Item/Product**: This is the name of the item you are billing for. You can either enter the details manually, or start typing and pick already invoiced items.
- **Description**: Add more information about the item. This will help the customer better understand the job completed, and is also useful for your own reference.
- **Unit Price**: The amount you charge per unit of items. For example, let's say your item is "1 hour consulting", and you charge $80 for an hour of consulting – that is, for 1 item unit. Then you'll enter 80 in the Unit Price field.

.. Note:: If you have selected a set item from the auto complete list, the description and unit price that you pre-defined in your previous invoice will apply by default. You can manually override the default unit price or description by clicking in field and changing the data.

- **Quantity**: The number of units being charged. Continuing the above example, let's say you need to charge for 3 hours of consulting, enter the number 3 in the Quantity field.
- **Tax Rate**: Note: To apply tax to the line item, click on the arrow at the right side of the Tax field and select the relevant tax from the drop-down list.
- **Discount**: This is the discount percentage you need to apply for the particular line item.

Click on **Save** button to save the item.

Beneath and to the right of the line item section, you'll find the Totals section:

- **Subtotal**: This is the amount due before other figures are taken into calculation, such as Tax, Discounts, Credits, etc.
- **Tax 1**: Tax 1 rate for the invoice.
- **Tax 2**: Tax 2 rate for the invoice.
- **Payment Made**: The amount paid to date, including partial payments and credits.
- **Balance**: The final balance owed to you, after taxes, partial payments and credits have been deducted from the charged amount.

Invoice Page
""""""""""""""""
- **Show to client button**: Use this button to hide/show invoice to client.
- **Pay Invoice button**: Click this button to make payment to an Invoice.
- **Email button**: Email the invoice directly via Workice system to the email address specified for the client.
- **Activity button**: Click to view invoice history.
- **Set Reminder button**: Add custom reminder and get alert. e.g Reminder to send invoice
- **Comments button**: Add invoice comments here.
- **More button**: Access additional invoice options including updating, deleting invoice.
- **Mark Sent**: When you mark an invoice as sent, only then is the invoice viewable to the client in the client portal, and the client balance is updated to reflect the invoice amount.
- **Mark Paid**: Manually mark the invoice as paid. You may want to do this if you are not entering the payment directly into the system.
- **Delete Invoice**: Click here to delete the invoice. It will be deleted and removed from the Invoices list page.
- **Share button**: Dispays a link that you can send to client to access the invoice.
- **PDF button**: Download a PDF version of the invoice.
- **As Client button**: You can impersonate a client and view the invoice as client.

.. TIP: You may attach invoice documents using the folder icon at the top right side of the invoice top navigation..

Email Invoice Preview
"""""""""""""""""""""

When you are ready to send an invoice to the client, click the Email Invoice button. Before the invoice email is sent, a pop-up box will open, displaying a preview of the email. Here, you can add additonal comment to the email.

Customizing the Invoice Email Template
''''''''''''''''''''''''''''''''''''''

To customize the email template, go to **Settings** - **Translations** and click on **Emails button** on the top navigation and select the locale you want to modify.

.. TIP:: You can customize any type of email template, including invoice emails, First Reminder, Second Reminder and Third Reminder emails. The english version variables are named in **module**, **action** and **message** format (dot notation). Example; if you need to edit the message that will be sent when you send an invoice, look for a variable named ``invoices.sending.body``. To edit sent message subject, modify ``invoices.sending.subject`` value.

Instant Notification
""""""""""""""""""""""
Know when an invoice is viewed, becomes due, or gets paid, so you can take the right actions to manage your cash flow. Set up invoice reminders to automatically email your customers when payment is due.

Reuse items as much as you want
""""""""""""""""""""""""""""""""""
Recycling is a good thing, so why waste time and effort writing in the same items and prices over and over again? Once you add your items to an invoice you'll only need to start typing in your invoices to see them pop up.

Auto Reminders
""""""""""""""""""
Save yourself the time and hassle and automate your client communications! An invoice reminder is an automatic email message to remind your customer that an invoice is coming due or that it is overdue. This is a great way to stay on top of reminding your customers that you should be getting paid soon. To enabled Invoice Reminders, modify your **.env** file and change the value of ``AUTO_REMIND_INVOICES`` to false to disable it. Default is ``true``.

.. TIP:: Modify the number of days to send each invoice reminder in **Settings** - **Invoice Settings** section. You may also set late fee to apply on third reminder.

Recurring Invoice
""""""""""""""""""
As a busy freelancer, you work for a variety of clients. Some jobs are one-off, but others are ongoing, whether on a weekly, monthly or other basis. Workice CRM recurring invoice feature automatically creates invoices for ongoing jobs, and sends the current invoice to the client on a regular, pre-defined basis. For each recurring job, you only need to set up the procedure once. 

To make a invoice recur, edit the invoice and select the **Recur Every** dropdown. You can set it to recur every ``week, month, quarter, six months and yearly``. Select the start date and a date when the invoice should stop recurring (End Date).

.. TIP:: To stop a recurring invoice, edit the invoice and change **Recur Every** field to **None**.

.. TIP:: Reminders are sent based on the due date of the invoice.

.. TIP:: To disable/enable sending invoices immediately they recur, go to **Settings** - **Invoice Settings** and disable/enable **Email on Recur** checkbox..

When the invoices from this invoice will be generated you will have an overview which invoices are generated from this invoice at the Child Invoices link on the invoice page.


Bulk Actions
""""""""""""""""

If you need to perform an action for a number of invoices, you can do it in one click with the bulk action feature. To use the bulk action feature, mark the relevant invoices in their checkbox at the far left of the invoices list. Once you've marked the invoices, select an action to perform on them in the buttons below the invoice list page.

- **Send**: Send selected invoices by email to client(s).
- **Mark as Paid**: Mark selected invoices as paid.
- **Archive**: Archive selected invoices.
- **Delete**: Delete selected invoices.