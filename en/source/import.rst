.. include:: termins.rst
.. _chapter_import:

Data Import
===========

Notification Import Tunes
-------------------------

Notification import tunes have the main role in the notifications import. Once
financial institution changes notification structure the import tunes should be changed too.
For that case you can download update or modify tunes by yourself, see chapter :ref:`chapter_notifications`.

.. image:: images/updateimporttunes-010-select-actions.png
  :width: 25%
.. image:: images/updateimporttunes-020-select-import.png
  :width: 25%
.. image:: images/updateimporttunes-030-select-import-sms-tunes.png
  :width: 25%

Select menu item |menu_actions_import_sms_import_settings| to get updates.

.. image:: images/updateimporttunes-040-select-import-tunes-updated.png
  :width: 25%
.. image:: images/updateimporttunes-050-select-import-tunes-new.png
  :width: 25%
.. image:: images/updateimporttunes-060-select-import-tunes-no-updates.png
  :width: 25%

The app will show available update, also it is possible to download new ones here.

.. image:: images/updateimporttunes-070-select-actions.png
  :width: 25%
.. image:: images/updateimporttunes-080-select-active_profile.png
  :width: 25%
.. image:: images/updateimporttunes-085-select-notifications.png
  :width: 25%

.. image:: images/updateimporttunes-090-check-use_exchange_when_wifi.png
  :width: 25%

But may be you will see nothing. Check the import tunes exchange is on at settings.

SMS and Push Notifications
--------------------------

The app |bb| imports SMS and push notifications by default. But it is possible to import
certain notification by hands. To do that

#. Open the import dialog.
#. Select a required account. The account should have the identity and the import tune.
#. Select required notifications.
#. Press |button_import| button.
#. Check transactions list for the result.
#. Use event log to view issues.

.. image:: images/manualsmsimport-010-select-actions.png
  :width: 25%
.. image:: images/manualsmsimport-020-select-import.png
  :width: 25%
.. image:: images/manualsmsimport-030-select-import-sms.png
  :width: 25%

.. image:: images/manualsmsimport-040-select-account.png
  :width: 25%
.. image:: images/manualsmsimport-050-move-next.png
  :width: 25%
.. image:: images/manualsmsimport-060-import-sms.png
  :width: 25%

.. image:: images/manualsmsimport-070-view-transactions.png
  :width: 25%
.. image:: images/manualsmsimport-080-view-events.png
  :width: 25%


CSV files
---------

During |csv| file import the app can create new accounts, categories, payers or payees,
projects, and persons. It depends on your choice.

The column separator can be one of  ";", ",", "|", "/", "\". File must be UTF-8 encoded.

The first row of the file must have column names in English, case does not matter.
Since column names are placed at another row they are valid for next rows.

.. list-table:: CSV file format
   :widths: 7 5 30
   :header-rows: 1

   * - Names
     - Mandatory
     - Comment
   * - id
     - No
     - Transaction identity, the app will search existed transaction if not empty.
   * - account
     - Yes
     - Name, number, or identity of the account
   * - date
     - No
     - Date of the transaction, supported formats: "dd'd'MM'd'yyyy" (for example, 01d01d2017), "yyyy'd'MM'd'dd" (for example, 2017d01d01), "yyyyMMddHHmmss", "yyyyMMddHHmm", "yyyyMMdd", "yyyy-MM-dd HH:mm:ss", "yyyy-MM-dd HH:mm", "yyyy-MM-dd", "dd-MM-yyyy HH:mm:ss", "dd-MM-yyyy HH:mm", "dd-MM-yyyy", "dd.MM.yyyy HH:mm:ss", "dd.MM.yyyy HH:mm", "dd.MM.yyyy"
   * - time
     - No
     - Time of the transaction, supported formats: "HH:mm:ss", "HH:mm", "HHmmss", "HHmm"
   * - amount
     - Yes
     - Transaction amount, can have a currency and digits delimiters, fixed point should be point or comma
   * - rate, exchange rate
     - No
     - Transaction rate
   * - currency
     - No
     - Transaction currency, account currency is used when empty
   * - payer, payee, contractor
     - No
     - Name of the contractor, the app will analyze current row keywords when empty
   * - category
     - No
     - Name of the category, the app will analyze current row keywords when empty
   * - project
     - No
     - Name of the project, the app will analyze current row keywords when empty
   * - person, unit
     - No
     - Name of the person, the app will analyze current row keywords when empty
   * - notes, note
     - No
     - Note
   * - planned, plan
     - No
     - Actual (0) or planned (1), default value is 0
   * - detail, split
     - No
     - Transaction (0) or detail of transaction (1). default value is 0

The row is canceled when mandatory columns are empty.

If the row contains not all mandatory columns, but amount column is not empty, then app creates split transaction. This is like column detail contains value 1.

To start the import

#. Open the import dialog.
#. Select a file.
#. Press |button_next| and select required rows.
#. Press |button_import| button.
#. Check transactions list for the result.
#. Use event log to view issues.

.. image:: images/csvimport-030-select-import-csv.png
  :width: 25%
.. image:: images/csvimport-040-select-file-and-options.png
  :width: 25%

OFX files
---------

|бб| supports import of |OFX| files meet specification starting from 2.1.1.

#. Open the import dialog.
#. Select a file.
#. Press |button_next| and select required rows.
#. Press |button_import| button.
#. Check transactions list for the result.
#. Use event log to view issues.

.. image:: images/ofximport-030-select-import-ofx.png
  :width: 25%
.. image:: images/ofximport-040-select-file-and-options.png
  :width: 25%
