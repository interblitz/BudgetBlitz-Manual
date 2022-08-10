.. include:: termins.rst
.. _chapter_directories:

Directories
===========

Directories are available from the top menu or from the |menu_actions_directories| menu.
It depends on the current screen.

.. image:: images/directories-010-select-directories.png
  :width: 25%
.. image:: images/directories-020-menu-directories.png
  :width: 25%

Portfolio Types
---------------

Portfolio types are used to separate dimensions between your activities. For example, one set of
categories is used for personal finance and another set is used for business finances. When you
edit a transaction its dimensions (category,  payer or payee, project, and person) correspond
to the certain type of portfolio.

.. image:: images/directories-030-types-of-portfolio.png
  :width: 25%
.. image:: images/directories-040-portfolios.png
  :width: 25%
.. image:: images/directories-050-accounts.png
  :width: 25%

It will be useful to pay attention to the |item_universal| type of portfolio. Its name is |item_category_empty|
for old versions. Dimensions of this type of portfolio are always available. For example |item_category_transfer|
category can be selected in any transaction regardless selected account and connected portfolio type.

.. note:: Dimensions of the |item_universal| type of portfolio are always available

Portfolios
----------

Portfolio is a group of accounts. Portfolio has own currency. The |бб| uses a portfolio currency
to show financial highlights. Use the |meta_dir_currencies| directory to apply currency rates.

Accounts
--------

Account is a bank account, debit or credit card, investment account, cash, or something else.
Account has own currency. It may be differ from a currency of portfolio.

Identity of an account is used for transactions import, see :ref:`chapter_import`.
You can put several identities. Use the comma to separate one identity from another.
Usually card or account number is used for identity. Phone number, or SMS sander name,
or identity of push notifications package can be considered as identity as well.

Key phrases are also used for transactions import. For transfers source account is detected by identity
and target account is detected by key phrases. Key phrases are used for transfers only.

For example you have SMS from bank:
::

  Visa2900 card. Cash withdraw 200.00 USD ATM 5412. Balance: 274.26 USD. 25/03/14,15:00:00.

Visa2900 is identity of the |item_card| account, ATM is the key phrase for the |item_cash| account.
Since SMS pushed the app |bb| will create two transactions, debit transaction on |item_card| account
and credit transaction on |item_cash| account.

SMS import tune establishes the algorithm of transactions detection. See more details in the :ref:`chapter_notifications`.

Default values of payers and payees, projects and persons are used when you create transaction
and import transactions, Also the app uses this values for teamwork on data exchange.

.. image:: images/directories-055-accounts-continue.png
  :width: 25%
.. image:: images/directories-060-categories.png
  :width: 25%
.. image:: images/directories-070-contractors.png
  :width: 25%

Categories
----------

|meta_dir_categories| directory plays the main role for the classification of transactions.
A category may a set of options,
|property_category_income|, |property_category_outcome|, |property_category_summary|,
technical, |property_category_eliminable| and  |property_category_archived_femail|.

Categories sorting order under transaction editing depends on
|property_category_income| and |property_category_outcome| options. For a revenue transaction
revenue categories are placed at the beginning and then expense ones placed and vice versa.

A category may be neither revenue nor expense. In that case the category is technical. For instance
technical category is used for credit limit changing. For that transaction there is no money turnovers
for a card owner but nevertheless balance is changed. See more details about credit limit at
`questions and answers (How to setup credit limit for new or existed account?)`_.

.. _`questions and answers (How to setup credit limit for new or existed account?)`: http://qa.bbmoney.biz/en/index.php?qa=27&qa_1=how-to-setup-credit-limit-for-new-or-existed-account

Since a category has |property_category_summary| option you can use |meta_report_debts| and |meta_report_plan_implementation|
reports to get there balance.

Sometimes you need to eliminate transactions from revenues and expenses. Usually it is
transfer transactions. Use categories with |property_category_eliminable| option for them.
The app has standalone totals at the main screen and transactions list for transfers and other transaction with
categories with |property_category_eliminable| option.

The app uses key phrases to find an item when importing transactions. You can set several
comma separated key phrases.

It is possible to define several categories for a transaction.

Once the app installed the directory of categories has default items. It's up to you edit, add, or delete them.

Payers and Payees
-----------------

Contrary part of transaction is payer or payee. This is often called a contractor. Only transfer transactions
have no contractor. Bat all other transactions have. Transaction have only one contractor.

Projects
--------

You can use projects to account vacations, startups, housing projects and so on.
Transaction may have several projects.

The app uses key phrases to find an item when importing transactions. You can set several
comma separated key phrases.

Persons
-------

You can use persons to account family members, company staffers and so on.
Transaction may have several projects.

The app uses key phrases to find an item when importing transactions. You can set several
comma separated key phrases.

.. image:: images/directories-080-projects.png
  :width: 25%
.. image:: images/directories-090-persons.png
  :width: 25%
.. image:: images/directories-100-currencies.png
  :width: 25%

Currencies
----------

Once the app installed it contains almost all world currencies. Of course you can add a new one.

Currency rates are used for calculate financial highlights. You can set rates manually
or load from internet resources. Available sources are European Central Bank,
Russian Central Bank (currencies and metals), Bank of Canada, National Bank of the Republic of Belarus,
National Bank of the Republic of Kazakhstan, Bank of Israel, BitPay (BTC rates), Poloniex (cryptocurrencies trading market).

Let author know if you need more, see :ref:`section_feedback`.
