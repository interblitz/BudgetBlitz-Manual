.. include:: termins.rst
.. _chapter_widgets:

Widgets and Templates
=====================

Widgets
-------

|bb| has the convenient widget to show actual balance, turnovers and to create new transaction.

.. image:: images/widget-480.png
  :width: 25%
  :align: center

Available size of widget are 1x1, 1x2, and 1x4. The widget theme and the app theme are equals.

You can use widget not only like a financial highlights. Other ways of usage are short report
and template of new transaction.

.. image:: images/widgets-005-widget-available.png
  :width: 25%
.. image:: images/widgets-010-widget-settings-open.png
  :width: 25%
.. image:: images/widgets-020-widget-settings.png
  :width: 25%

A new widget contains a balance and turnovers for the current day. Press |button_settings|
to modify widget.

The |section_view| section has main widget options.

Use the |property_name| when you have more than one widget. You can keep it empty if you want to.

Use the |property_portfolio_types|, the |property_portfolios| and the |property_accounts| options
to restrict information of widget. You can put one or more values. Different widgets
can have different options. For example you can have two widgets, one for
certain account, and another for another one.

Use the |property_show_balance| to set balance visibility on or off. Also you can specify
whether credit limit is ignored or not when balance is calculated.
Balance is free of credit limit by default and for credit cards
you will have a negative balance.

.. image:: images/widgets-030-widget-settings-2.png
  :width: 25%
.. image:: images/widgets-040-widget-settings-apply.png
  :width: 25%

Using Widgets as Transaction Templates
--------------------------------------

The |button_new_transaction| button is available in the widget since account for new transactions specified in
settings. Also you can set an amount for new transaction. That amount will be copied to a new transaction.

Values of a filter will be copied to a new transaction as well.

Thus, you can use widget like a new transaction template.

.. note:: Templates are available in the Pro version. Free version ignores an amount and values of filter.

Using Widgets as Reports
------------------------

Since widget has flexible settings you can use it as a report with persistent settings. The
|section_filter| section is the key.

.. note:: Widgets as reports are available in the Pro version.

Widgets as Reports Example
--------------------------

Let us make a widget setup to show public transport expenses during current month.
Open widget settings and put the |value_public_transport| name.

.. image:: images/widgets-050-widget-example-set-name.png
  :width: 25%
.. image:: images/widgets-060-widget-example-select-period.png
  :width: 25%
.. image:: images/widgets-070-widget-example-select-period-apply.png
  :width: 25%

Set balance off, because we do not need to see totals. Select current month as the time range.

.. image:: images/widgets-080-widget-example-select-budget-item.png
  :width: 25%
.. image:: images/widgets-090-widget-example-select-budget-item-apply.png
  :width: 25%
.. image:: images/widgets-100-widget-example-settings-apply.png
  :width: 25%

Set the |item_category_public_transport| category and save settings.

.. image:: images/widgets-110-widget-example.png
  :width: 25%

Now you can see turnovers under |item_category_public_transport| category for the current month,
expenses amount, and accounts that are the source of payments.

Widgets as Templates Example
----------------------------

Now, modify settings the way you can fast create expenses. Open the setting to do that.

.. image:: images/widgets-120-widget-example-select-account.png
  :width: 25%
.. image:: images/widgets-140-widget-example-select-amount.png
  :width: 25%
.. image:: images/widgets-150-widget-example-select-amount-value.png
  :width: 25%

Set the account you will pay often for public transport. Also put the most frequent amount.

.. image:: images/widgets-160-widget-example-select-amount-value-2.png
  :width: 25%
.. image:: images/widgets-170-widget-example-settings-apply.png
  :width: 25%
.. image:: images/widgets-180-widget-example-transaction-new.png
  :width: 25%

Save settings. Now the button to create new transaction appeared.

.. image:: images/widgets-190-widget-example-transaction.png
  :width: 25%

Create new transaction and you will see one contains the account, the amount and the category already.
All you have left to do is save the new transaction.

Using same way you can put payer, payee, project, and person for a new transaction. Each new
template should have a new widget.
