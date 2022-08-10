.. include:: termins.rst
.. _chapter-account-identities:

Account Settings for Notifications Import
=========================================

Identity Choosing
-----------------

You have to put an identity at the account card before import SMS or push notifications.
This will ensure detection of an account for a transaction. Usually financial institutions
put last four digits of a card number to a notification. So use them as a card identity.

For a example, for the SMS
::

  VISA1234: 08.08.13 14:05 payment 500.00 USD. balance 1000.00 USD.

you should choose VISA1234 as a card identity. Some financial institutions do not put
digits of an account or card number into notifications. For example, in the SMS
::

 Transaction >> -600 USD.	Atm-nyc-001

there is no way to find out an identity. Well, in that case you should use
sender name or number. For example, short number for Sberbank is 900.
For push notifications sender is a package identity. For example,
ru.rocketbank.r2d2 is the package identity for RocketBank.

Open the card of an account in order to setup identity. Press |spinner_account_identity| and
select identity from a financial institution message. Put the identity by hands
if you want to use sender or package identity.

Also do not forget to select an import tune for your financial institution.

.. image:: images/accountidenties-005-select-references.png
  :width: 25%
.. image:: images/accountidenties-010-select-accounts.png
  :width: 25%
.. image:: images/accountidenties-020-open-card-account.png
  :width: 25%

.. image:: images/accountidenties-030-scroll-to-identity.png
  :width: 25%
.. image:: images/accountidenties-035-select-identity.png
  :width: 25%
.. image:: images/accountidenties-040-set-identity.png
  :width: 25%

Key Phrase Choosing for Transfers
---------------------------------

The app |bb| can create transfer transactions based upon financial institution messages. For example, when you
have an SMS
::

  VISA1234: 08.08.13 14:05 cash withdrawal 200.00 USD. ATM 10010001 bal 500.00 USD.

then the app is able to create expense transaction for the VISA1234 account and revenue transaction
for a cash account. All you need is to set key phrases for the cash account. The app will
use this key phrases to find out the one. For example, key phrases above may be one of "cash withdrawal" or
"ATM".

.. note:: It is also necessary to ensure the app is able to identify a transaction as transfer, see :ref:`chapter_notifications`.

Open the card of an account in order to setup key phrases. Press |spinner_key_phrases| and
select ones from a financial institution message. Also put key phrases by hands
if you want to.

.. image:: images/accountidenties-050-open-cash-account.png
  :width: 25%
.. image:: images/accountidenties-060-scroll-to-keywords.png
  :width: 25%
.. image:: images/accountidenties-070-set-keywords.png
  :width: 25%

Usually accounts having notifications have empty |property_keywords| property and cash accounts
have empty |property_identity| property vice versa. But there are rare cases when both ones are used. See Rocketbank_
notifications import setting.

.. _Rocketbank: http://qa.bbmoney.biz/ru/index.php?qa=67&qa_1=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D1%80%D0%BE%D0%BA%D0%B5%D1%82%D0%B1%D0%B0%D0%BD%D0%BA%D0%B0&show=68#a68
