Expenses
========
.. meta::
   :description: Workice CRM makes it easy to keep track of your spending. This article shows you how to add an Expense, as well as set up recurring Expenses and even re-categorizing them.
   :keywords: projects, invoices, deals, leads, crm, estimates, tickets, subscriptions, tasks, contacts, contracts, creditnotes

Track all of your lunch meetings or training materials, and other miscellaneous expenses in the Expenses section, and instantly bill clients.
Expenses allow you to capture the billable and non-billable costs that you incur as part of your project work. These non-labor expenses are usually itemized costs for things like materials, travel expenses, or fixed-fee services. Typically, billable expenses are passed on to a client or customer, whereas non-billable expenses are internal costs paid for by your employer.

.. TIP:: You can create Expenses that you incur as part of your business operations (for example, Internet Expenses), or Recurring Expenses for those charges you incur on a frequent basis. 

List Expenses
"""""""""""""

To view the Expenses list page, click on the Expenses tab on the main sidebar.

Overview
^^^^^^^^

The Expenses list page displays a list of all business expenses that you choose to enter. The table columns appear as below;

- **Code**: Reference number for the expense
- **Client**: The name of the client for whom the expense is relevant
- **Project**: The name of the project attached to the expense
- **Amount**: The expense amount including taxes
- **Billed**: Whether the expense has been billed to client
- **Category**: The assigned category of the expense
- **Expense Date**: The date the expense occurred

Expense Categories
""""""""""""""""""

`Workice <https://workice.com>`__ makes it easy to keep track of your spending with Expenses with categories to organize them. 

Workice also makes it easy for you to create your own custom categories if a specific one isn't available. 

Adding/Editing Categories
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Click on the **Gears** icon at the topbar of the expenses list page. A modal will popup with a list of all existing categories. Here you can add, edit and delete your expenses categories.

How Taxes Work on Expenses
""""""""""""""""""""""""""""""""
.. ATTENTION:: When creating an Expense with a tax on it, the system will automatically calculate taxes for you based on the total amount you paid.

Here’s a sample tax situation:

You paid $113.00 in gas (including tax) while driving around the city.
 - Enter $113 into the first required Amount
 - Choose a Tax. In this case it is HST = 13%.
 - The system will calculate that you paid $13.00 in Tax to make the total $113.

Create Expense
""""""""""""""

You can create a new expense directly from the Expenses list page by clicking on the **Create** button located at the top right side of the page. A modal will open for you to enter expense information.

- **Amount**: The amount of the expense.
- **Category**: Select the category from the drop-down list.
- **Vendor**: If you have already saved a vendor, you'll only need to start typing and it will auto complete.
- **Currency**: Select the currency of the expense.
- **Tax 1**: Enter tax 1 as percentage.
- **Tax 2**: Enter tax 2 as percentage
- **Notes**: Enter a description of the expense. When the expense is converted to an invoice, the text you enter here will feature as the line item description for the expense on the invoice.
- **Project**: Select a project attached to the expense
- **Expense Date**: Date when the expense incurred
- **Recurring**: Whether the expense should recur
- **Billable**: Whether the expense is billable
- **Show to Client**: Hidden or visible to client
- **Billed**: Whether the expense is already billed
- **Tags**: Custom tags e.g internet,rent etc
- **Receipts**: Upload expense receipts


Recurring Expenses
"""""""""""""""""""
Some expenses are incurred on a consistent basis over a period of time, and manually recording them each time can get really tedious. Generating these expenses can be automated in Workice, resulting in systematic tracking.

To make an expense recur, edit the expense and modify **Recur Every** field.

You can set a repeat interval such as ``daily, week, month, quarter, six months, year``.

Once you have chosen the interval, you can decide for the repeat to stop by a particular date.

.. TIP:: To stop a recurring expense, edit the expense and change **Recur Every** field to **None**.


Invoice Expense
""""""""""""""""""""""

Are you billing a client directly for an expense? To bill an expense, first create an invoice for the client. Open the new invoice and just below the Client address, you'll see a red button **Expenses Available** click on the button to open the modal where you can select the expenses to include in the invoice.
