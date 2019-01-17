Subscriptions
=============
.. meta::
   :description: Take the hassle out of using separate systems to manage your sales leads and subscriptions.
   :keywords: projects, invoices, deals, leads, crm, estimates, tickets, subscriptions, tasks, contacts, contracts, creditnotes

Subscriptions feature helps you bill customers for your services once or on a recurring basis. Effortlessly manage the entire customer life cycle, from onboarding a customer for a subscription plan to accepting payments.
Once a subscription has been created, it will begin to auto-renew on the period specified by the product to which it is related. There’s not much you need to do, other than keep tabs on them from time to time looking for subscriptions that go sour.

.. ATTENTION:: Subscription payments is provided via `Stripe <https://dashboard.stripe.com>`__ you will need to have active Stripe account in order to use this feature. More subscription integrations will be included in future releases.

.. ATTENTION:: For subscriptions to work, you need to configure Stripe Keys. Check **Configure** under installation section of this documentation for more details.

.. TIP:: If you haven’t created your products and billing plans, you should create via the Stripe Dashboard, `Workice CRM <https://workice.com>`__ will fetch the billing plans directly from Stripe and will display them while creating/updating subscription.

Getting Started
"""""""""""""""
Start by creating your stripe products on Stripe Dashboard.

 - Click on **Create** button in subscriptions list page.
 - If you have setup your Stripe configuration correctly, you should get a popup modal with the fields below;

- **Name** - Subscription name that will be shown to the customer
- **Billing Date** - First billing date field, leave blank to use the date when the customer is subscribed to the subscription.
- **Client** - The name of the client
- **Stripe Plan** - Retrieved from your stripe account.(Your Stripe Products)
- **Description** - Subsscription description

.. ATTENTION:: To view subscriptions that a client has not subscribed, click on **Plans** button.

After you have created a subscription for the client, click on **Plans** table to view the subscription, modify, delete or send it to your customer.
Your client will see the subscription on their dashboard where they can subscribe.

.. TIP:: A new role named ``subscriber`` will be created/attached to the customer primary contact.

Cancel Subscription
""""""""""""""""""""
If you want to cancel subscription from the admin section, you can open the subscription and click on the cancel button; 

Cancel Immediately
^^^^^^^^^^^^^^^^^^^
If you click Cancel Immediately, the subscription will be cancelled immediately and not option to reactivate.

Cancel on expiry
^^^^^^^^^^^^^^^^^^^
If the Cancel Immediately checkbox is left unchecked, the subscription will cancel at the end of billing period and you'll have an option to re-activate it.

Subscription Invoices
"""""""""""""""""""""
Your client/customer can download their invoices by clicking on **Invoices** button at the top bar of subscriptions list page.
