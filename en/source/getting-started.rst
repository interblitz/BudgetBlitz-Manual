.. include:: termins.rst

Getting Started
===============

In this chapter it is suggested a certain sequence of actions for setting up the application. If you don't like that, you don't have to.  Just remember you can change any option later.

Basic customization
-------------------

Edit basic settings after the first start. To do that use the menu |menu_actions_profile|
to open settings directory.

.. image:: images/gettingstarted-010-main-screen.png
  :width: 25%
.. image:: images/gettingstarted-020-click-on-actions-menu.png
  :width: 25%
.. image:: images/gettingstarted-030-settings.png
  :width: 25%

Here you can:

- set a secret key pattern to restrict app access;
- set SMS and push notifications parser on or off;
- set synchronization between devices on or off;
- set default sign for money amount for new transactions;
- set profile currency and source for currency exchange rates;
- set an automatic backups;
- set upcoming payment notifications on or off;
- set ring tones for when transactions created via SMS and push notifications parser.

While basic settings are ready you can go deeper. Next steps you can see on the main screen.

Loading bank settings
---------------------

This section is intended for those who plan to use automatic creation of transactions on SMS or push notifications arrived
from bank or payment systems or other installed apps.

This is requirements for automatic transactions creation on SMS push:

#. the option should be on, see menu |menu_actions_profile|;
#. the app should have access to SMS (Android 6+).

This is requirements for automatic transactions creation on push notification (use menu |menu_actions_profile|):

#. you should select packages to import push notifications:
#. you should grant access rights to the app.

Press the button |button_sms_import_settings| to load setting of your bank or payment system. Hereafter
to do that use menu |menu_actions_import_sms_import_settings| or directory
|meta_dir_sms_import_tunes|.

.. image:: images/gettingstarted-050-click-on-import-tunes.png
  :width: 25%
.. image:: images/gettingstarted-060-available-sms-tunes.png
  :width: 25%

Portfolio and account settings
------------------------------

Once installed the app has three portfolio types |item_personal|, |item_small_business|, |item_universal|,
one personal portfolio |item_wallet|, two accounts |item_card|, |item_cash| and default list of the categories.

Values to show depend on the portfolio type of the transaction.  For example,
one categories list is used for personal finances and another for a small business finances.
But nevertheless there are some common categories. Universal type of the portfolio is used
for this values. Universal values shown regardless portfolio type of the transaction.

A portfolio is like a group of accounts. On the main screen the app groups accounts by portfolios and
calculates summary.

Make the required amount of portfolios and accounts. See :ref:`chapter-account-identities` to use automatic transactions creation
via SMS or push notifications.

Now you can import SMS or import initial transactions from |csv| и |ofx| or just enter initial balance. Once you have at least one transaction
created main screen will show a summary and buttons will disappear.

Initial data import
-------------------

First of all check account settings according chapter :ref:`chapter-account-identities`. Then press |button_sms_import_items|
int the Import section or select menu |menu_actions_import_sms_import_items|, select an account
and import notifications. See more details in the chapter :ref:`chapter_import` и `вопросах и ответах`_.

.. _`вопросах и ответах`: http://qa.bbmoney.biz/ru/index.php?qa=13&qa_1=%D0%BA%D0%B0%D0%BA-%D0%B2%D1%80%D1%83%D1%87%D0%BD%D1%83%D1%8E-%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-sms&show=13#q13

Also you can import initial transactions from file |csv| or |ofx|. Check and edit CSV file before import according to chapter :ref:`chapter_import`. OFX file
no need any modifications.

Entering initial balance and credit limit
-----------------------------------------

You can enter initial account balance via transaction. The date of transaction can be arbitrary but it is highly proffered to make transaction first in the transactions list.
Another important thing is to use category |item_category_initial_balance| for that transaction.

.. image:: images/initialbalance-010-initial-transaction.png
  :width: 25%
.. image:: images/initialbalance-020-initial-budget-item.png
  :width: 25%

As well as initial balance you can enter credit limit via transaction too. It is preferred that the transaction date coincide with the date of setting the limit by the bank.
Use |item_category_credit_limit| category. Please pay attention that it is a technical category with
|property_category_income| and |property_category_outcome| set off. You can see more details about such an approach reasons
at `вопросах и ответах (Как задать кредитный лимит)`_.

.. _`вопросах и ответах (Как задать кредитный лимит)`: http://qa.bbmoney.biz/ru/index.php?qa=93&qa_1=%D0%B7%D0%B0%D0%B4%D0%B0%D1%82%D1%8C-%D0%BA%D1%80%D0%B5%D0%B4%D0%B8%D1%82%D0%BD%D1%8B%D0%B9-%D0%BB%D0%B8%D0%BC%D0%B8%D1%82-%D0%BD%D0%BE%D0%B2%D0%BE%D0%B3%D0%BE-%D1%81%D1%87%D0%B5%D1%82%D0%B0-%D1%81%D1%87%D0%B5%D1%82%D0%B0-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D0%BE%D0%BC%D1%83-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D0%B8

.. image:: images/initialbalance-040-credit-limit-transaction.png
  :width: 25%
.. image:: images/initialbalance-050-credit-limit--budget-item.png
  :width: 25%

It would be better to enter each debt or credit with two transactions. For example you have a credit of 1000 |c|. So you should

#. make a positive transaction with amount of 1000 |c| using category |item_category_credit| and a real contractor or person.
#. make a negative transaction with amount of 1000 |c| using category |item_category_empty| or real one if known.

As result the balance is equal zero, but Debts report will show the value of your loan.
