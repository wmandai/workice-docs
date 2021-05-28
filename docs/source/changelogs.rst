Changelogs
==========
Version 3.0.8 - 28 May 2021
"""""""""""""""""""""""""""""""
- Fixed issue with creating deals

Version 3.0.7 - 25 May 2021
"""""""""""""""""""""""""""""""
- Fixed issue with viewing deals
- Fixed issue in calculating taxes
- Upgraded Laravel Version
- Added 3 decimals support for taxes
- Fixed showing hidden expenses to client
- Updated css/js assets
- Fixed issue with adding/updating item templates
- Added mailgun endpoint to .env

Version 3.0.0 - 25 November 2020
"""""""""""""""""""""""""""""""
- Fixed mark invoice as paid date issue.
- Updated to Laravel 8
- Added Square Payment Gateway
- Added tax per item and tax types to invoices.
- Fixed issue with uploading files
- Added option for compound and simple taxes
- Modified Gantt to include Milestones
- Fixed downloading files permissions
- Added laravel livewire and tailwindcss
- Added custom company address formatting in settings
- Added shipping and billing addresses to invoices, estimates and creditnotes
- Added easymde markdown editor with autosave
- Added discounts per item
- Added Gocardless direct mandates
- Upgraded 2checkout payment
- Added contract signature pad
- Added AWS Pinpoint SMS
- Added Shoutout SMS
- Added Telegram notifications
- Added Messagebird SMS
- Search field on top nav now searches for everything not only tags
- Added logged in devices in user profile
- Fixed deal and lead stages calculations
- Added option to make knowledgebase public
- Added option to display Bank account on Invoices when enabled
- Task progress percentage calculated using task checklist
- Fixed many known bugs

Version 2.1.5 - 15 December 2019
"""""""""""""""""""""""""""""""
 - Added staff timecards
 - Added gocardless direct debit
 - Added Invoicr PDF engine
 - Upload WYSIWYG images to folder instead of base64 encode to database
 - Fixed copying project issue
 - Fixed Project Template not copying milestones,tasks etc
 - Added option to disable discount and tax columns on estimates/invoices
 - Fixed bulk invoice payments
 - Fixed tasks today count on top header
 - Fixed importing csv
 - Fixed issue with saving todo
 - Show error when invoice overpaid
 - Create tickets for only registered users
 - Fixed language, permission and translations 404 error
 - Added correct cron path on Settings > System Info page
 - Added invoice recurring biennially
 - Fixed invoice double taxation

Version 2.1.2 - 25 September 2019
"""""""""""""""""""""""""""""""
 - Added Aircall integration (sync)
 - Upgraded to Laravel 6 LTS
 - Added html editor for texts (Summernote)
 - Added Project Custom Fields
 - Added SMS integration (Inbound/Outbound - Twilio)
 - Added Bulk SMS to leads
 - Updated Stripe Subscriptions (SCA Rules)
 - Added option to manually very user accounts
 - Changed WhatsApp driver to Wablas
 - Added Github Issues integrations with Project Issues
 - Added Contract Templates
 - Fixed known issues

Version 2.1.0 - 15 June 2019
"""""""""""""""""""""""""""""""
 - Added WhatsApp integration via ApiWha
 - Added WhatsApp Opt-In
 - Added unlimited recurring option (without end dates)
 - Fixed next recurring dates for recurring invoices,expenses and tasks
 - Fixed Onesignal issue
 - Added support and lead custom email senders
 - Added option to set default application locale
 - Added project feedback report
 - Send notifications via WhatsApp
 - Changed datatables to POST from GET
 - Added option to increase number of digits for invoices
 - Fixed known issues

Version 2.0.9 - 28 May 2019
"""""""""""""""""""""""""""""""
 - Added project templates
 - Added Pagseguro payment for brazil
 - Added more dashboard stats
 - Fixed todo list URL
 - Added web to lead form
 - Fixed font in PDFs
 - Added convert deal to project
 - Added custom item units
 - Fixed attaching projects to tickets
 - Added notification to team when task created
 - Fixed known issues


Version 2.0.8 - 13 May 2019
"""""""""""""""""""""""""""""""
 - Fixed invoices and estimates public link responsive
 - Fixed Nexmo SMS
 - Fixed PDF fonts
 - Fixed files not showing in user profile
 - Added search contacts
 - Fixed adding items conflict in creditnotes
 - Fixed calendar locale
 - Fixed time format in client dashboard
 - Added default company logo if missing
 - Fixed stage_id required error when importing deals
 - Fixed lead stage calculations
 - Fixed invoice auto reminders

Version 2.0.7 - 08 May 2019
""""""""""""""""""""""""""""""
 - Fixed quick access issue when task/project deleted.
 - Fixed notification not sent to task creator
 - Fixed PDF for shared estimates
 - Fixed PDF download for contracts by client
 - Added paytm for India
 - Fixed customer verification
 - Made activities clickable
 - Show social logins individually
 - Fixed send email when ticket status changed
 - Fixed files without title not downloadable
 - Transfer notes to deals when lead is converted to deal
 - Transfer notes to client comments when lead is converted to customer
Version 2.0.6
"""""""""""""""
 - Add button to compute analytics in Reports
 - Fixed date issue when importing data from old system
 - Fixed email files not setting correct adapter
 - Fixed missing translation strings
 - Added run cron via URL
 - Fixed show task name for running timer

Version 2.0.5
"""""""""""""""
 - Fixed deleting contact issue
 - Fixed reset password hashing twice
 - Fixed PDF not showing image

Version 2.0.4
"""""""""""""""
 - Fixed archiving projects when importing from freelancer
 - Fixed issue in cancelling invoices
 - Fixed invoicing project issue
 - Fixed error displaying deals in staff dashboard

Version 2.0.3
"""""""""""""""
 - Added artisan commands execution
 - Fixed ticket assignment error
 - Fixed deleting user observer

Version 2.0.2
"""""""""""""""
 - Fix importing old data
 - Fixed installation company name containing white space
 - Fixed department filter in tickets
 - Fixed Recaptcha

Version 2.0.1
"""""""""""""""
 - Fix help me link not working in dashboard
 - Lock exchange rates
 - Option to update invoices, estimates, credits and expenses exchange rates
 - Fixed knowledgebase rating issue
 - Added option to turn off project feedback email
 - Fixed Paypal Live IPN issue
 - Added invoice overpayment alert

Version 2.0.0 - 01 May 2019
"""""""""""""""""""""""""""""

- Initial release
