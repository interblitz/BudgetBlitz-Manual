.. include:: termins.rst
.. _chapter_api:

API
===

You can integrate |bb| with other applications. For example, you can connect |bb|
with a voice assistant and create transactions by voice. Another hint is to create
transactions using `Tasker`_.

.. _`Tasker`: https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm

To create a new transaction you just need to send |var_intent_convert_text_to_transaction| broadcast intent.
Since intent received the app analyze it and create new transaction using notifications detection algorithm.

Intent must provide parameters by the extra section:

#. |var_timestampMillis|: Type of long, date and time of a new transaction in milliseconds. Current date and time used when empty.
#. |var_address|: Type of String, sender of the message, can be empty.
#. |var_message|: Type of String, message like a notification to create a new transaction, required.
