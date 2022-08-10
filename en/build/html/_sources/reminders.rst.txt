.. include:: termins.rst
.. _chapter_reminders:

Reminders
=========

|бб| can remind you about some important events based upon reports or transactions list. Reminders
may be one-time or recurring. Using reminders you are able to:

  *  Customize notifications about no category transactions.

  *  Customize notifications about specific transactions.

  *  Customize warnings about plan and actuals difference.

  *  Customize warnings about any events you can find with reports.

  *  Run reports on a schedule.

.. note::
  You can access to the report from notification using version Pro

First of all you need to specify criteria for events that will produce notifications.
To achieve that edit and save report setting having required filters and grouping, see
:ref:`chapter_shortcuts`.

As far as setting is ready make reminder for it using |button_reminders| button or from |meta_dir_reminders|
directory.

.. note::
  Beginning from Android 4.4 the accuracy of the reminders is +/- 15 minutes.

Let's take a look at example of creating a reminder about transactions with an empty category.
On the home screen move to the transactions list.

.. image:: images/reminders-010-main-screen.png
  :width: 25%
.. image:: images/reminders-020-main-screen-swipe-left.png
  :width: 25%
.. image:: images/reminders-030-main-screen-transactions.png
  :width: 25%

Edit the filter so that transaction list has only ones with an empty category.

.. image:: images/reminders-040-transactions-bottom-sheet-opening.png
  :width: 25%
.. image:: images/reminders-050-transactions-bottom-sheet-open.png
  :width: 25%
.. image:: images/reminders-060-report-filter.png
  :width: 25%

.. image:: images/reminders-070-report-filter-category.png
  :width: 25%
.. image:: images/reminders-080-report-filter-apply.png
  :width: 25%
.. image:: images/reminders-090-report-filter-applied.png
  :width: 25%

After the filter applied, transactions list has changed, it now contains only two items. Let's
save the filter into report setting. Open bottom side for that and pressing on |spinner_list_view_settings|
create a new report setting. You can modify period of setting but now we leave it unchanged.

.. image:: images/reminders-100-report-select-new-setting.png
  :width: 25%
.. image:: images/reminders-100-report-setting-save.png
  :width: 25%
.. image:: images/reminders-110-report-view-settings-alarms.png
  :width: 25%

Now let's create reminder base upon new report setting. Move to reminders list and make a new one.
Specify date of beginning, time of running, recurrence type and a name. You will see the name
in a notification that produced by reminder.

.. image:: images/reminders-120-alarms-new.png
  :width: 25%
.. image:: images/reminders-130-alarms-edit.png
  :width: 25%
.. image:: images/reminders-140-alarms.png
  :width: 25%

Reminder is ready, now we will test it. Select reminder and press |button_reminders_run|.
In the status bar you see notification about transactions with an empty category.

.. image:: images/reminders-150-alarms-select.png
  :width: 25%
.. image:: images/reminders-160-alarms-run.png
  :width: 25%
.. image:: images/reminders-170-alarm_notification.png
  :width: 25%

You can press on notification to preview list of transactions.

.. note::
  Only Pro version allows moving to data of notifications.

Now you will see notification every day at the specified time when
you have one or more transactions with an empty category.
