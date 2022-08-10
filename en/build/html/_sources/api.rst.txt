.. include:: termins.rst
.. _chapter_api:

Integration with third party applications
=========================================

You can integrate |bb| with other applications. For example, you can connect |bb|
with a voice assistant and create transactions by voice. Another hint is to create
transactions using `Tasker`_.

.. _`Tasker`: https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm

-----------------------------
Making Transactions From Text
-----------------------------

To create a new transaction you just need to send broadcast intent. Since intent received the app analyze it
and create new transaction using notifications detection algorithm.

Intent parameters are

Class = |var_intent_convert_text_to_transaction|

Extras:

#. |var_timestampMillis|: Type of long, date and time of a new transaction in milliseconds. Current date and time used when empty.
#. |var_address|: Type of String, sender of the message, can be empty.
#. |var_message|: Type of String, message like a notification to create a new transaction, required.

.. _sub_chapter_rest_api:

--------
REST API
--------

|bb| supports `REST API`_. API allows to create new directories and transactions, and edit or delete existed ones. Using
this API you can create your own addons or applications.

.. _`REST API`: https://github.com/interblitz/BudgetBlitz-Api

You have to enable remote access to dial with `REST API`_ and read documentation, see chart :ref:`chapter_remote_access`.
Documentation is available by `Swagger`_. On the `Swagger`_. page type the address  http://[server]:[port]/api/v1/docs.json.
Server and port will be available after PC connection enabled.

.. _`Swagger`: https://interblitz.github.io/BudgetBlitz-Api/swagger/

You can try app examples at the `github.com`_. After an exmple has loaded type |bb| address as http://[server]:[port].

.. _`github.com`: https://github.com/interblitz/BudgetBlitz-Api

-----------
Intents API
-----------

In addition to simple API for making transactions from text |bb| supports extended Intents API. It consists of two parts,
events and data requests. API based on the REST API. By default Intents API is OFF. You have to enable it
selecting the part you need.

~~~~~~~~~~~~~~~~~~~~~~~~~~~
Intents API: Part 1, Events
~~~~~~~~~~~~~~~~~~~~~~~~~~~

When directories and transactions are saving events occurs. On the event |bb| sends Intent. You have to select target
packages in the settings. Intent contains:

Action = |var_action_api_event_ITEM_ONCHANGE|

Extras:

#. |var_collection| - collection name that fires event
#. |var_id| - object id that fires event

When transaction is coming from notification import Extras contains

#. |var_notification| - notification text
#. |var_address| - notification address (phone number or package name)
#. |var_amount| - transaction amount
#. |var_currency| - transaction currency

To get more data you should send request Intent.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Intents API: Part 2, Requests
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Request intents intended to get, modify or delete some data. Intent structure is

Class = |var_intent_api_request|

Action = |var_action_api_request|

Extras:

#. |var_method| - single value from: GET, POST, DELETE
#. |var_path| - path to the collection
#. |var_body| - JSON data
#. |var_package| - full package name to receive response, response will not return if empty
#. |var_class| - package class to receive response, may be empty

Also Extras can contain any other data. All that data will returned back in response.

|bb| sends Intent response witt structure

Action = |var_action_api_response|

Extras:

#. |var_collection| - collection name
#. |var_response| - JSON response

Parameters |var_method|, |var_path|, |var_body|, |var_collection|, |var_response| matches REST API. Documentation is available from the `Swagger`_.
See more :ref:`sub_chapter_rest_api`.
