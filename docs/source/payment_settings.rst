Payment Settings
=====================
You can view and edit the payment configuration in your CRM by going to **Settings** and clicking on the **Payment Settings**.

.. NOTE:: Supported payment gateways are **paypal, stripe, mollie, razorpay, checkout, braintree, bank, wepay**

You can modify the settings as below;

 - **Payment Prefix**: Add your chosen transactions prefix. Default PAY 
 - **Payment Number Format**: Estimate format. Default -[yyyy][mm][dd]-[i] for {year}{month}{day}-{number}
 - **Payment Gateways**: Enabled payment gateways separated by a comma
 - **Paypal Live**: Enabled live paypal payments or sandbox
 - **Paypal Email**: Your Paypal email address for receiving payments
 - **2checkout Live**: Enable Live/Sandbox payments via 2Checkout
 - **Braintree Live**: Enable Live/Sandbox payments via Braintree
 - **Braintree Merchant Account**: Default Braintree merchant account
 - **Wepay Live**: Enable Live/Sandbox payments via WePay
 - **Bank Details**: Your Bank information to be displayed to client incase they need to pay via Bank
   
Adding Custom Gateway
"""""""""""""""""""""""
`Workice <https://workice.com>`__ allows you to integrate with 3rd-party payment gateways or services. The following steps summarize how to develop a custom payment gateway:

 - Create a payment gateway form that allows customers to enter any required payment data.
 - Create a custom payment gateway provider class that performs the required payment processing.
 - Map the payment gateway provider to the appropriate payment form by registering a custom implementation of the PaymentInterface interface.
 - (Optional) Create an IPN handler for your payment gateway.
 - Open **Settings > Payment Settings** and add the name of your custom gateway to the list of comma separated Payment Gateways.
 - Customers on your portal can now select the custom payment method during checkout and pay for their invoices using the given gateway.
   
Creating payment gateway forms
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
 - Start by creating a file named **form.blade.php** in ``Modules\Payments\Resources\views\{gateway}\form.blade.php`` where ``{gateway}`` is the name of your custom gateway.
 - We recommend you to take a look at the other gateways files in order to get the idea. The form submits to a custom controller (we'll create it later).
 - Create a route in ``Modules\Payments\Http\custom.php`` (There is a sample route in the file). Your form should use this route to submit data to the controller.
 - Inside your custom payment gateway **form.blade.php** before closing your form add this line **@include(\'payments::_includes._options\')** this will show options to the client i.e Pay Full amount or partial amount.
 - Create a Controller in ``Modules\Payments\Http\Controllers`` e.g ``ExampleGatewayController``.
 - Inside this controller handle checkout request when the form is submitted. Take a look at ``Modules\Payments\Http\Controllers\Base`` controllers for an idea on how to implement your checkout method.
 - After initializing and processing the payment in controller checkout method, now verify the payment and post the data to ``PaymentEngine`` helper as shown below;

.. code-block:: shell

 // Check if payment successfull
 if ($charge->paid == true) {
  // Pass the data to PaymentEngine class as shown below
  // Replace {gateway} with your gateway name
  $payment = (new \Modules\Payments\Helpers\PaymentEngine('{gateway}', $charge))->transact();
 }


Now create your payment gateway class in ``Modules\Payments\Gateways`` to parse data and save to Workice CRM.
If your custom gateway is named **{example}** ensure this file is named **Example.php**. This class must extend ``Modules\Payments\Contracts\PaymentInterface`` interface.
Take a look at how the other payment gateways are parsing data and submits it to ``Modules\Payments\Helpers\Cashier`` class.

.. code-block:: shell

 public function pay($transaction)
 {
  // Get the invoice from the database
  $this->invoice = $this->invoice->findOrFail($transaction->orderId);
  // The getData() method returns formatted array of data to be passed to Cashier class.
   $data = $this->getData($transaction);
  // Pass the transaction data to Cashier as first parameter 
  // The second parameter is the invoice object
   return (new Cashier($data, $this->invoice))->save();
 }

Handling IPN for custom payment gateways
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
If you wish to use Instant Payment Notification (IPN) with your payment gateway, you need to create a custom HTTP handler that performs the required communication between your Workice application and the payment service. Do not handle IPN requests using standard pages (web forms).

We recommend creating IPN controller in ``Modules\Webhook\Http\Controllers`` and add a route in ``Modules\Webhook\Http\routes.php``.
Implement your IPN verification and send the data to the PaymentEngine as shown below;

.. code-block:: shell

 // {gateway} is the name of your gateway and {data} is the transaction data
 $txn = (new \Modules\Payments\Helpers\PaymentEngine('{gateway}', {$data}))->transact();


.. ATTENTION:: To enable your custom gateway, add it to the list of active payment gateways in **Settings > Payment Settings > Payment Methods**
