Tickets
=======
.. meta::
   :description: Easily deal with customer support tickets, create knowledgebase to provide the best possible support for your freelance services.
   :keywords: projects,invoices,freelancer,deals,leads,crm,estimates,tickets,subscriptions,tasks,contacts,contracts,creditnotes,freelancer office,codecanyon

Tickets are the means through which your end users (customers) communicate with agents in your support system. `Workice <https://workice.com>`__ support system allows you to present a web portal to your customers to create, track, and respond to support requests.
Regardless of the type of customer support you provide, the one constant for all support organizations is that customers seek you out to help them resolve their issues. 

Here are some of the options that your customers have for contacting you:
 - Send an email
 - Fill out a support request form in your Workice Support portal
 - Fill out a support request form on your own web site (Use Ticket API)

.. NOTE:: By default, a comment you enter as a Public Reply will be public and visible to everyone who views this ticket, including the person who requested support. You can also add private comments (referred to as an Internal Note). The requester never sees these notes, they are used for internal communication only. For example, an agent may need to get advice from another agent to solve the requester's support issue. 

If you want to add an internal note, start your comment with **[NOTE]**

Example internal note;

.. code-block:: shell

	[NOTE] My internal note comment

Create Ticket
"""""""""""""
To create a ticket, click **Create** button on the ticket list page. You will be redirected to the create ticket page where you can enter ticket information.

 - **Department**: The department a ticket is associated with

 .. Note:: Custom fields will be displayed based on the selected department.

 - **Subject**: Ticket subject e.g Billing Issue
 - **Reporter**: The ticket reporter
 - **Project**: Select a project (if any) associated with the ticket.
 - **Priority**: Ticket priority (low, medium, high)
 - **Message**: Ticket body/message
 - **Tags**: Custom tags e.g logos, design etc
 - **Files**: Attach ticket files e.g screenshots

Convert Ticket to Task
""""""""""""""""""""""""
To convert a ticket to task, open the ticket and click **Convert to task** button. 
A popup modal will appear where you can select a project you want the task created. Click **Ok** to complete the action.

Change Ticket Status
"""""""""""""""""""""
To change the status of a ticket including closing a ticket, open a ticket and click on **Status** button and select your preferred status from the dropdown list.

Bulk Actions
""""""""""""""""

If you need to perform an action for a number of tickets, you can do it in one click with the bulk action feature. To use the bulk action feature, mark the relevant tickets in their checkbox at the far left of the tickets list. Once you've marked the tickets, select an action to perform on them in the buttons below the ticket list page.

- **Close**: Close selected tickets
- **Archive**: Archive selected tickets.
- **Delete**: Delete selected tickets.
  
Customer Satisfaction Ratings
""""""""""""""""""""""""""""""""
If you enable Customer Satisfaction Ratings in Workice Support, your customers will receive an email notification after their ticket has been solved asking them to rate their support experience. You can modify the number of days before a rating request is sent in **Settings** > **Ticket Settings** > **Feedback Request**. Setting it to ``zero`` will disable the feature.

AnswerBot
"""""""""""
Answer Bot works right alongside your support team to help answer your customers’ questions. With content from your Workice knowledge base, Answer Bot suggests articles to your customers to resolve their issues. The customer reviews the articles and if an answer is found, they can mark their question as answered and close the ticket.