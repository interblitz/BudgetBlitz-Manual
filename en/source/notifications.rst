.. include:: termins.rst
.. include:: <isonum.txt>
.. _chapter_notifications:

Advanced Import SMS and Push Notifications Setting
==================================================

Notifications Detection Algorithm
---------------------------------

The import tune ensures the process of SMS and push notification detection. Exactly import
tune controls type of transaction, revenue, expense or transfer, is balance required or not,
and so on.

You can see the algorithm of notifications detection at the picture below.

.. image:: images/sms-import-algorithm-en.png
  :width: 75%
  :align: center

When new notification arrived then the app tries to detect an account. It uses identities from the
|meta_dir_accounts| directory. Since single account found the app loads connected import tune.

Further the app classifies transaction, revenue, expense, or transfer, based on the import tune.
While transaction is transfer the app tries to find a target account. Now it uses key phrases from the
|meta_dir_accounts| directory. Since single target account found the app makes a target transaction
in order to complete transfer.

Next stage is to select dimensions. The app tries to find a category, payer or payee, project, person
based on there key phrases. Default values is used when no value found out.

Finally the app calculates amount and balance. Additional commission or correction
transaction can be made or currency rate calculated when balance from notification is not equal to the app one.
It depends on a context and transaction currency.

Sometimes notifications arrive in a wrong order not like a real transactions done. The app
creates balance correction transactions in that case until the order becomes correct.
The app will remove redundant corrections as far as possible after the order becomes correct.

Example

1. 13.04.2016, 10:00, balance = 1000 |c|

The app got messages, sequence is invalid, correct one is 4, 3, 5, 2.

2. 13.04.2016, 15:00, expense = -50 |c|, balance = 500 |c|, |rarr| automatic correction = -450 |c|
3. 13.04.2016, 15:05, expense = -90 |c|, balance = 800 |c|, |rarr| automatic correction = +390 |c|
4. 13.04.2016, 15:10, expense = -110 |c|, balance = 890 |c|, |rarr| automatic correction = +200 |c|
5. 13.04.2016, 15:15, expense = -250 |c|, balance = 550 |c|, |rarr| automatic correction = -90 |c|

The app got message that starts correct sequence.

6. 13.04.2016, 15:20, expense = -100 |c|, balance = 400 |c|, |rarr| automatic correction  = 0 |c|, automatic corrections  2 --- 5 removed

New Custom Import Tune
----------------------

At this moment |bb| has more than 160 ready to use import tune for world wide financial institutions.
It is not to match of course. But you can create an import tune by yourself with little effort.
It is very easy to do.

.. image:: images/notificationsimporttunes-010-select-directories.png
  :width: 25%
.. image:: images/notificationsimporttunes-020-select-import-tunes.png
  :width: 25%
.. image:: images/notificationsimporttunes-030-select-new.png
  :width: 25%

|property_name| for new setting can be different. It would be nice to make a name th same as
financial institution.

|property_import_tune_restriction_by_sender| is only used in quite unique cases when the app is not able
to identify account. That restriction fires before the app looking for an account by identity making list
of accounts shorter.

Let the app has two accounts, for example

  #. RocketBank, the identity is ru.rocketbank.r2d2, the import tune is RocketBank;
  #. VTB, the identity is \*\*\*1234, the import tune is VTB.

RocketBank, the sender is ru.rocketbank.r2d2, sends notification about revenue as
::

  Transaction >> +1 800 USD.
  Source card is «VTB ***1234»

There is no identity in this notification but there is the transfer source account number. Without
restriction by sender the app can not find the RocketBank account, because both accounts
RocketBank and VTB are suitable.

Since the restriction is on, the app finds RocketBank import tune by sender ru.rocketbank.r2d2.
Only RocketBank account uses that setting, so the app selects RocketBank account correctly.

The basic options of the import are established by key phrases. An option may have one or more
comma separated key phrases.

|property_import_tune_keywords_in_out| define transaction sign. The import is not possible when
sign is undefined.

|property_import_tune_keywords_transfer| indicate to the app two transactions instead one required.
The transfer direction depends on the transaction sign.

Let the setup be, for example, as:

  #. Revenues key phrases: "cash deposits,credit"
  #. Transfers key phrases: "cash deposits"
  #. Account Card identity: Visa2900
  #. Account Cash key phrases: "ATM"

Bank sends notification:
::

 Card Visa2900. Cash deposits 200.00 USD ATM. Balance: 2740.26 USD. 25/03/14,15:00:00.

As a result, the app will create two transactions:

  #. Revenue transaction for Card account;
  #. Expense transaction for Cash account.

.. image:: images/notificationsimporttunes-040-import-tune.png
  :width: 25%
.. image:: images/notificationsimporttunes-050-import-tune-2.png
  :width: 25%

Sometimes certain notifications have a balance and certain have not. Special
key phrases help the app to understand when is case to calculate balance and when is not.

Sometimes notification is for information only but contains revenue or expense key phrases.
|property_import_tune_keywords_skip| key phrases makes possible to cancel import.

Example

  #. Revenues key phrases: "cash deposits,credit"
  #. Skip transaction key phrases: "error"
  #. Account Card identity: Visa2900

Bank sends notification:
::

 Card Visa2900. Cash deposits 200.00 USD ATM. Balance: 2740.26 USD. An error occurred. 25/03/14,15:00:00.

As result, the app will not make a transaction. And it is the case, because ATM have made a money back not
a cash deposits.

|property_import_tune_position_amount| is the most probable place of the amount. Final
decision is up to the app.

|property_import_tune_position_balance| is the most probable place of the balance. Final
decision is up to the app too.

Put -1 when where is no balance in notifications at all.

The app skips all notification without balance when |property_import_tune_position_balance| is not equal -1.
But you can specify key phrase to underline when is app have to expect balance and when have not to.

Transaction amount and balance are used to calculate currency rate, commission, and correction.

Near the money amount of transaction should be placed a currency. Left of or right of, it does not matter.
Currency names and keywords are the glue for the app find it out.

Certain financial institutions not always put currency in notifications. Use
|property_import_tune_no_currency| in that case and the app will use the currency of account.
