.. include:: termins.rst
.. _chapter_transactions:

Transactions
============

Introduction
------------

Transactions are used to account any changes in funds. So use a transaction when you need to
enter an initial balance, change a credit limit, store crediting or debiting funds,
store cash withdrawal at ATM, or something else. This approach is most versatile. The history of
all movements will be stored due to that approach and you will be able to recall any transaction
you need.

.. image:: images/transactions-010-transactions.png
  :width: 25%
.. image:: images/transactions-015-transactions-bottom-sheet-opening.png
  :width: 25%
.. image:: images/transactions-016-transactions-bottom-sheet-open.png
  :width: 25%

You can use filters and fast time range selection at the transactions list.

.. image:: images/transactions-017-transactions-dates-range-swipe.png
  :width: 25%
.. image:: images/transactions-018-transactions-dates-range-spinner.png
  :width: 25%
.. image:: images/transactions-020-transaction.png
  :width: 25%

Transaction has to be one of revenue or expense. There is no special option just put positive
or negative amount. For transfer use categories with |property_category_eliminable| option.
Since installed the app contains |item_category_transfer| category you may apply to.

For a foreign transaction you should put a currency and it's rate. This rate can be different from
a rate stored in the |meta_dir_currencies| directory. The app by itself calculates currency and rate
for transactions imported from SMS and push notifications.

Use transaction dimensions, categories, payers, payees, projects, and persons to get a comprehensive
funds accounting.

Splits
------

You can divide transaction for details. It is often called as make a :term:`split`.
When you have a check in a supermarket it is convenient to make a split to store
food costs, household goods costs, and so on. Of course it is far from the only case.

The app always calculates first part of a split by itself. Just put amounts of others.
Put zero amount to remove redundant part.

.. image:: images/transactionsplit-010-select-transaction.png
  :width: 25%
.. image:: images/transactionsplit-020-transaction-details.png
  :width: 25%
.. image:: images/transactionsplit-030-transaction-edit-detail.png
  :width: 25%
.. image:: images/transactionsplit-040-transaction-details-row-second.png
  :width: 25%
.. image:: images/transactionsplit-050-transaction-details-row-first.png
  :width: 25%

Planned Transactions
--------------------

Transactions are one of actual or planned. The option |property_transaction_planned| is used
for a planned transaction. The app takes into account planned transaction until they have expired.
A date and time of a transaction is a key for expiration. You can plan any funds movement,
expenses, revenues, debts, credits, and so on. Reports will help you to
compare actuals and plans.

.. image:: /images/transactionplan-010-transaction-set-plan.png
  :width: 25%

Manual Transfers
----------------

The app stores transfer within two transactions. There is a fast and convenient way to make
a transfer from a transaction card.

#. Make a new transaction and put an amount.
#. Select the |button_tranfer| button near the source account.
#. Select target account and the app will make the rest.
#. Edit other options if you want to.
#. Save the target transaction.
#. You will see transfers amount at the main screen.

.. image:: images/transactionstransfer-010-create-transaction.png
  :width: 25%
.. image:: images/transactionstransfer-020-transaction-edit.png
  :width: 25%
.. image:: images/transactionstransfer-030-transaction-select-transfer.png
  :width: 25%
.. image:: images/transactionstransfer-040-transaction-select-transfer-account.png
  :width: 25%
.. image:: images/transactionstransfer-045-transaction-select-transfer-account.png
  :width: 25%
.. image:: images/transactionstransfer-050-transaction-edit-save.png
  :width: 25%
.. image:: images/transactionstransfer-070-transfer-result.png
  :width: 25%

At this moment source and target transactions are not connected to each other.
Do not forget to edit both ones in future.

Recurring Transactions
----------------------

Many transactions happen with some frequency. Usually recurring transactions
are planned but sometimes actual too.

You can establish a custom frequency for recurring transactions.

.. image:: images/recurringtransactions-010-select-directories.png
  :width: 25%
.. image:: images/recurringtransactions-020-select-recurring-transactions.png
  :width: 25%
.. image:: images/recurringtransactions-030-select-transaction.png
  :width: 25%
.. image:: images/recurringtransactions-040-reccuring-transaction.png
  :width: 25%
